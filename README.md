# Ansible Collection - szorfein.hardening

Enhance security of system based on GNU/Linux for a better default, i try to keep it the most minimal possible without settings a lot of variables or having to rewriting all the config files or writing custom scripts.

This collections follow recommendations from:

- https://theprivacyguide1.github.io/linux_hardening_guide.html
- https://madaidans-insecurities.github.io/guides/linux-hardening.html

Get few settings from:

- https://github.com/Kicksecure/security-misc
- Secureblue: https://github.com/secureblue/secureblue/tree/live
- https://github.com/dev-sec/ansible-collection-hardening

Last lynis test:

```txt
Lynis security scan details:

Hardening index : 82
Test Performed: 236

Scan mode:
Normal [V]
```

Collection tested on:

- Debian 11
- Archlinux
- Voidlinux

## Include Roles

- [os](https://github.com/szorfein/ansible-collection-hardening/tree/main/roles/os)
- [ssh](https://github.com/szorfein/ansible-collection-hardening/tree/main/roles/ssh)

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
  vars:
    os_fix_ntp: false
    sshd_x11_forwarding: "yes"
```
