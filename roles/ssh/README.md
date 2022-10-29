ssh
===

A role that configures SSH with the best security options. The defaults pass audit scanners successfully:
- [Lynis](https://cisofy.com/lynis/)
- [ssh-audit](https://github.com/jtesta/ssh-audit)

Links:
- https://stribika.github.io/2015/01/04/secure-secure-shell.html

Requirements
------------

None.

Role Variables
--------------

- `sshd_allow_group`
  - Default: `ssh-user`
- `sshd_allow_agent_forwarding`
  - Default: `'no'`
- `sshd_allow_tcp_forwarding`
  - Default: `'no'`
- `sshd_client_alive_count_max`
  - Default: `2'`
- `sshd_compression`
  - Default: `'no'`
- `sshd_log_level`
  - Default: `'VERBOSE'`
- `sshd_max_auth_tries`
  - Default: `3`
- `sshd_max_sessions`
  - Default: `2`
- `sshd_password_authentication`
  - Default: `'no'`
- `sshd_permit_root_login`
  - Default: `'no'`
- `sshd_tcp_keep_alive`
  - Default: `'no'`
- `sshd_x11_forwarding`
  - Default: `'no'`


To allow an user to use ssh, use `allowed_users`, they will be inserted in group called `ssh-user` by default.

```yml
allowed_users: [ ansible ]
```
Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      become: true
      collections:
        - szorfein.hardening
      roles:
         - { role: szorfein.hardening.ssh, allowed_users: [ ansible ] }

License
-------

MIT
