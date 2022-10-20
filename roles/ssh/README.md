secure_shell
=========

Enhance Security of SSH.

Helped with:
- Lynis
- Ssh-audit
- https://stribika.github.io/2015/01/04/secure-secure-shell.html

Requirements
------------

None.

Role Variables
--------------

To allow user to accept ssh connection, they will be inserted in group called `ssh-group` by default.

```yml
allowed_user: [ ansible ]
```

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      become: true
      roles:
         - { role: szorfein.secure_shell, allowed_users: [ansible] }

License
-------

MIT
