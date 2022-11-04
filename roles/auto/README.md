szorfein.hardening.auto
=======================

A role to automatically do things via systemd or a cron job, like system update.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

- `auto_update`
  - Default: `false`
- `auto_update_clean_day`
  - Default: `6`
  - Description: Clean your installer (apt-get, pacman) cache | orphan | old kernel every n-day.
- `auto_update_download_pkgs_day`
  - Default: `1`
  - Description: Downloads only pkgs on your system every n-day.
- `auto_update_upgrade_day`
  - Default: `3`

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

    - hosts: servers
      become: true
      collections:
        - szorfein.hardening
      roles:
         - { role: auto, auto_update: true }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
