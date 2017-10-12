# Hermod

## Getting started

You will need to map the hostname `lightsail` to the address of your
instance, either the public IP address or a URL if you have already set up
DNS.

You can do this by changing the inventory file
[`inventory.yaml`](/inventory.yaml) to the following:

```yaml
all:
  hosts:
    lightsail:
      ansible_host: ip_address
      vars:
        ansible_python_interpreter: /usr/bin/python3
```

where ip_address should be changed to the public IP of your instance (or URL).
Alternatively you can set the address in your `~/.ssh/config` as follows:

```
# Lightsail
Host lightsail
    user ubuntu
    HostName ip_address
    IdentityFile ~/.ssh/key_file_that_you_use
```

Then you run ansible on your local machine as follows:

```bash
ansible-playbook -i ./inventory.yaml lightsail.yaml
```
