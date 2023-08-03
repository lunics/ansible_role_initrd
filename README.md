# Ansible role: INITRD

Generate the init RAM disk on Arch Linux.

## Usage
Override [defaults]() and see [vars]()

### Example for a BTRFS root partition on LVM on LUKS.
Enable one on these:
```yaml
luks_enable:  true
lvm_enable:   true
btrfs_enable: true
btrfs_multi_devices: false
```
Will be the same as declaring:
```yaml
mkinitcpio_config:
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

Inspired from [aisbergg](https://github.com/aisbergg/ansible-role-mkinitcpio)
