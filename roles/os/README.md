szorfein.hardening.os
=====================

A brief description of the role goes here.

Requirements
------------

None.

Role Variables
--------------

- `os_fix_core_dumps`
  - Default: `true`
- `os_fix_core_login_defs`
  - Default: `true`
- `os_fix_permissions`
  - Default: `true`
- `os_auth_crypt_rounds`
  - Default: `20000`
- `os_auth_pass_max_days`
  - Default: `180`
- `os_auth_pass_min_days`
  - Default: `7`
- `os_umask`
  - Default: `'027''

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    - hosts: servers
      collections:
        - szorfein.hardening
      roles:
         - { role: szorfein.hardening.os, x: 42 }

License
-------

MIT
