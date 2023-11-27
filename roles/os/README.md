szorfein.hardening.os
=====================

- Block and blacklist ~50 modules with modprobe.
- Hide processes currently running on the system for users.
- Configure pam to use strong passwords with libpwquality.
- Disable core dumps.
- Corrects permission on sensitive files and directory.
- Configures kernel parameters via sysctl.
- Mitigate CPU vulnerabilities by install microcode and configure kernel cmdline.
- Replace [NTP](https://blog.hboeck.de/archives/863-Dont-update-NTP-stop-using-it.html) by [secure-time-sync](https://github.com/szorfein/secure-time-sync).
- `/etc/securetty` is kept empty unless configured.

Requirements
------------

None.

Role Variables
--------------

- `os_fix_cmdline`
  - Default: `false`
  - Description: Configure cmdline with GRUB (cat /proc/cmdline) to limit vulnerability (CPU, system, ...).
- `os_fix_core_dumps`
  - Default: `false`
  - Description: Core dumps contain the recorded memory of a program, we stop it.
- `os_fix_cpu_microcode`
  - Default: `false`
  - Description: Install the last microcode (amd or intel).
- `os_fix_hidepid`
  - Default: `false`
  - Description: Hide pid run as root for normal user.
- `os_fix_login_defs`
  - Default: `false`
  - Description: Configure /etc/login.defs, password AGE, ENCRYPT_METHOD, SHA_CRYPT_ROUNDS, UMASK...
- `os_fix_modprobe`
  - Default: `false`
  - Description: Block a lot of unused/old mods for Linux (see them with
    the command lsmod).
- `os_fix_ntp`
  - Default: `false`
- `os_fix_pam`
  - Default: `false`
  - Description: Install pam-libpwquality and configure it.
- `os_fix_permissions`
  - Default: `false`
  - Description: Use a lot of 0600 and 0700 on sensitive files.
- `os_fix_securetty`
  - Default: `false`
  - Description: Limit terminals allowed for root. configure sudo or doas before applying this.
- `os_fix_sysctl`
  - Default: `false`
  - Description: Apply hardened rules with sysctl.
- `os_fix_umask`
  - Default: `true`
  - Description: Fix the value of umask on /etc/profile, /etc/login.defs, etc...
- `os_auth_crypt_rounds`
  - Default: `20000`
  - Description: Use something between 1000-999999999, your default system should use something like 5000.
- `os_auth_pass_max_days`
  - Default: `180`
- `os_auth_pass_min_days`
  - Default: `7`
- `os_mount_boot_cmd`
  - Default: `None`
  - Description: If need to mount a `/boot` and|or `/efi` partition before update Grub, type the full command, e.g: `mount /boot && mount -t vfat /efi`.
- `os_umask`
  - Default: `'027'`
  - Description: Default value to apply to umask, the default on all Linux is 022.
- `os_auth_ttys_list`
  - Default: `'[]'`
  - Description: Value to apply to securetty, the default disable all terminals. See your current file `cat /etc/securretty`.

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
