## Explanation

According to the [ArchWiki](https://wiki.archlinux.org/title/Gamescope), Gamescope requires the `nvidia_drm.modeset=1` kernel parameter when running on NVIDIA GPUs.

As explained by an NVIDIA forum moderator on [NVIDIA Developer Forums](https://forums.developer.nvidia.com/t/understanding-nvidia-drm-modeset-1-nvidia-linux-driver-modesetting/204068/2), enabling this parameter sets the `DRIVER_MODESET` capability flag in the nvidia-drm devices so that DRM clients can use the various modesetting APIs. In addition to allowing clients to talk to the low-level DRM interface, it’s also necessary for some PRIME-related interoperability features.

The downside, if you want to call it that, is that loading nvidia-drm with `modeset=1` causes it to configure and initialize all GPUs immediately rather than waiting for a client to open the `/dev/nvidia*` device files.

## Usage

To enable this flag, edit your boot entries under `/boot/loader/entries/`.

You should have some thing like this:

```
title   Arch Linux
linux   /vmlinuz-linux
initrd  /initramfs-linux.img
options root=UUID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx rw 
```

Add `nvidia_drm.modeset=1` to the end of the `options` line.

## Confirmation

To verify that the parameter was applied successfully, run the following command:

```
cat /proc/cmdline
```

Then check whether `nvidia_drm.modeset=1` appears in the output.