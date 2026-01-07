# Changelogs

- Change cmdline with Grub by using template
- Linux-hardened also install headers when available
- Apply code linter
- Block ICMP request

### Options name (new) change

- `os_use_kernel_hardened`: default false
- `os_fix_grub` instead of `os_fix_cmdline`
- `os_disable_ipv6`: default false

### Disabling more modules

- Intel telemetry
- Bluetooth
- Joystick
- Intel Management Engine (ME)

## v0.15.0, december 2023

- entropy > add pkg `rng-tools` when available.
- sysctl > add `vm.swapiness=1`.
- audit > install and configure `auditd`.
