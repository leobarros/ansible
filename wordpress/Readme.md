# Wordpress with Ansible

Learning ansible and creating a CMS Wordpress automatized.

## Tools

- Vagrant
- Ansible
- wordpress (and your stack)

## Issues with UNREACHABLE

Into the the directory ssh_keys create a new ssh key:

`ssh-keygen -t rsa`

Put the new key in thes directory and type the password `vagrant`

## Copying the new keys to vms

`ssh-copy-id -i vagrant_id_rsa.pub vagrant@<ip>`

For this project this ips are:

- wordpress (172.17.177.40)
- database (172.17.177.42)

Type the command in your terminal:

```bash
ansible all -i hosts -u vagrant --private-key ssh-keys/vagrant_id_rsa -m ping -m shell -a 'echo Hello, World'
```

The output will be:

```bash
172.17.177.42 | CHANGED | rc=0 >>
Hello, World
172.17.177.40 | CHANGED | rc=0 >>
Hello, World
```
