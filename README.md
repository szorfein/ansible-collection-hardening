# Ansible Collection - szorfein.hardening

Collection tested on:
+ Archlinux
+ Debian 11
+ Voidlinux

## Include Roles

+ [auto](https://github.com/szorfein/ansible-collection-hardening/tree/main/roles/auto)
+ [os](https://github.com/szorfein/ansible-collection-hardening/tree/main/roles/os)
+ [ssh](https://github.com/szorfein/ansible-collection-hardening/tree/main/roles/ssh)

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

## Example playbook

```yml
- hosts: localhost
  collections:
    - szorfein.hardening
  roles:
    - szorfein.hardening.os
    - szorfein.hardening.ssh
    - szorfein.hardening.auto
  vars:
    os_fix_ntp: false
    sshd_x11_forwarding: 'yes'
    auto_update: true
```
