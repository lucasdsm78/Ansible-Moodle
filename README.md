# Ansible-Moodle

## Prérequis
- Vagrant
- VirtualBox
- Ansible

## Architecture

Le déploiement utilise deux serveurs distincts:
- **web** : Serveur Apache + PHP hébergeant l'application Moodle
- **db** : Serveur MySQL dédié à la base de données

### Fichiers importants
- `hosts` : Définit les serveurs cibles pour Ansible
- `vault/vault.yml` : Contient les informations sensibles (mots de passe, etc.)
- `playbooks/` : Contient les playbooks pour installer Moodle et MySQL
- `roles/` : Contient les rôles personnalisés pour Moodle

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
