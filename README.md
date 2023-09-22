# Ansible role: INITRD

Generate the init RAM disk on Arch Linux.
Inspired from [aisbergg](https://github.com/aisbergg/ansible-role-mkinitcpio).

## Usage
Override [defaults](https://github.com/lunics/ansible_role_initrd/blob/main/defaults/main.yml) and see [vars](https://github.com/lunics/ansible_role_initrd/blob/main/vars/main/hooks_busybox.yml).

```yaml
mkinitcpio_config:      # is the same as below because it is automatically completed by default
  MODULES:
    - btrfs

mkinitcpio_config:      # more explicit declaration
  MODULES:
    - btrfs
  HOOKS:
    - base
    - udev
    - usr
    - resume
    - keyboard
    - btrfs
    - autodetect
    - modconf
    - block
    - keymap
    - consolefont
    - encrypt
    - lvm2
    - filesystems
  COMPRESSION: zstd
```
