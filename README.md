# Ansible Collection - szorfein.hardening

Collection tested on:
+ Debian 11
+ Archlinux
+ Voidlinux

## Include Roles

+ [secure_shell]()
+ [os](https://github.com/szorfein/ansible-collection-hardening/tree/main/roles/os)

## Install

Edit or create a `requirements.yml`
```yml
---
collections:
  - name: https://github.com/szorfein/ansible-collection-hardening.git
    type: git
```
And with ansible-galaxy:

    ansible-galaxy install -r requirements.yml

Or just with:

    ansible-galaxy collection install git+https://github.com/szorfein/ansible-collection-hardening.git

## Usage

```yml
- hosts: localhost
  collections:
    - szorfein.hardening
  roles:
    - szorfein.hardening.os
  vars:
    ssh_port: 44444
```
