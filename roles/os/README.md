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
  - Description: Core dumps contain the recorded memory of a program, we stop it.
- `os_fix_login_defs`
  - Default: `true`
  - Description: Configure /etc/login.defs, password AGE, ENCRYPT_METHOD, SHA_CRYPT_ROUNDS, UMASK...
- `os_fix_pam`
  - Default: `true`
  - Description: Install pam-libpwquality and configure it.
- `os_fix_permissions`
  - Default: `true`
  - Description: Use a lot of 0600 and 0700 on sensitive files.
- `os_fix_sysctl`
  - Default: `true`
  - Description: Apply hardened rules with sysctl.
- `os_auth_crypt_rounds`
  - Default: `20000`
  - Description: Use something between 1000-999999999, your default system should use something like 5000.
- `os_auth_pass_max_days`
  - Default: `180`
- `os_auth_pass_min_days`
  - Default: `7`
- `os_umask`
  - Default: `'027'`

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    - hosts: servers
      collections:
        - szorfein.hardening
      roles:
         - { role: szorfein.hardening.os, os_auth_crypt_rounds: 65536 }

License
-------

MIT
