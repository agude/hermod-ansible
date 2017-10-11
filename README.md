# Hermod

## Getting started

Run the following script on Lightsail when created:

```bash
apt-get install ansible -y
```

Then you will need to map the hostname `lightsail` to the address of your
instance, either the public IP address or a URL if you have already set up
DNS. You can do this in your `~/.ssh/config` file as follows:

```
# Lightsail
Host lightsail
    user ubuntu
    HostName ip_address
    IdentityFile ~/.ssh/key_file_that_you_use
```

Where you should change the `HostName` and `IdentityFile` to the right values
for your instance and ssh key. You can instead set it in the `hosts` file in
this repo, in which case you should add the lines:

```
[lightsail]
ip_address
```

Then you can run the ansible from the base of the repository as follows:

```bash
ansible-playbook -i ./hosts lightsail.yaml
```
