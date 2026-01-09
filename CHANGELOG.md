# Changelogs

## 0.25.0 - Jan. 2026

- Change cmdline with Grub by using template
- Linux-hardened also install headers when available
- Block ICMP request
- Secure-time-sync on a cron job all the 30 minutes
- Update Pam rules, config for faillock and libpwquality
- Apply code linter

### Options name (new) change

- `os_use_kernel_hardened`: default false
- `os_fix_grub` instead of `os_fix_cmdline`
- `os_disable_ipv6`: default false
- `os_modprobe_blacklist_usb`
- `os_modprobe_blacklist_cdrom`
- `os_modprobe_blacklist_webcam`
- `os_modprobe_blacklist_bluetooth`

### Disabling more modules

- Intel telemetry
- Bluetooth
- Joystick
- Intel Management Engine (ME)

## v0.15.0, december 2023

- entropy > add pkg `rng-tools` when available.
- sysctl > add `vm.swapiness=1`.
- audit > install and configure `auditd`.
