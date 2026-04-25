**systemd-boot** automatically scans for `.conf` files in `/boot/loader/entries`. You can create or modify these files manually. The existing entries are excellent starting points. Here are some entry examples:

Example 1 (Vanilla):
```
# Created by: archinstall
# Created on: 2024-08-22_18-30-31
title   Arch Linux (linux)
linux   /vmlinuz-linux
initrd  /initramfs-linux.img
options root=PARTUUID=3e8e72d2-1ff1-4f48-85f6-33e8a345e1df zswap.enabled=0 rootflags=subvol=@ rw rootfstype=btrfs
```

Example 2 (Zen):
```
# Created by: archinstall
# Created on: 2024-08-22_18-30-31
title   Arch Linux Zen
linux   /vmlinuz-linux-zen
initrd  /initramfs-linux-zen.img
options root=PARTUUID=3e8e72d2-1ff1-4f48-85f6-33e8a345e1df zswap.enabled=0 rootflags=subvol=@ rw rootfstype=btrfs
```
