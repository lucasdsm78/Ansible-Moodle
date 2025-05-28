# Ansible-Moodle

## Prérequis
- Vagrant
- VirtualBox
- Ansible

## Architecture

The deployment uses two separate servers:
- **web** : Apache + PHP server hosting the Moodle application
- **db** : MySQL server dedicated to the database

### Important files
- `hosts` : Defines target servers for Ansible
- `vault/vault.yml` : Contains sensitive information (passwords, etc.)
- `playbooks/` : Contains playbooks for installing Moodle and MySQL
- `roles/` : Contains custom roles for Moodle

## Installation of Moodle using Ansible

Run ./commands.shError
Error: Database connection failed

It is possible that the database is overloaded or otherwise not running properly.

The site administrator should also check that the database details have been correctly specified in config.php

You can see the docs of geeurgeerlingguy.mysql role :
https://galaxy.ansible.com/ui/standalone/roles/geerlingguy/mysql/documentation/

## Use with Vagrant
If you use Vagrant, you have to change the hosts file to add the following lines:
```
[web]
web ansible_host=192.168.56.10 ansible_user=root

[db]
db ansible_host=192.168.56.11 ansible_user=root
```

Then, run :
```bash
vagrant up
```
