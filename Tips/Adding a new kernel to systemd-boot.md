First, create a copy of your original kernel entry located in the `/boot/loader/entries/` directory.

Example:
```
sudo cp /boot/loader/entries/2024-08-22_18-30-31_linux.conf /boot/loader/entries/zen_linux.conf
```

Next edit the newly created file and add the information for the kernel you want to use. For exemple, this is the entry for my original kernel:
```
# Created by: archinstall
# Created on: 2024-08-22_18-30-31
title   Arch Linux (linux)
linux   /vmlinuz-linux
initrd  /initramfs-linux.img
options root=PARTUUID=3e8e72d2-1ff1-4f48-85f6-33e8a345e1df zswap.enabled=0 rootflags=subvol=@ rw rootfstype=btrfs
```

In my case, since I was adding the Zen kernel, I only needed to change 'linux' to 'linux-zen'. Here’s the result:
```
# Created by: archinstall
# Created on: 2024-08-22_18-30-31
title   Arch Linux Zen
linux   /vmlinuz-linux-zen
initrd  /initramfs-linux-zen.img
options root=PARTUUID=3e8e72d2-1ff1-4f48-85f6-33e8a345e1df zswap.enabled=0 rootflags=subvol=@ rw rootfstype=btrfs
```
