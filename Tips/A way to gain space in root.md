# Pacman Cache Management

Pacman stores downloaded packages in `/var/cache/pacman/pkg/` and does **not** automatically remove older or uninstalled versions. This behavior has some benefits:

1. You can **downgrade a package** without needing to fetch an older version from elsewhere (e.g., the [Arch Linux Archive](https://wiki.archlinux.org/title/Arch_Linux_Archive)).
2. If a package was **uninstalled**, it can be reinstalled directly from the cache — no need to redownload it from the repository.

However, it's important to **manually clean the cache periodically**, as it can grow significantly over time.

To manage this, you can use the [`paccache`](https://man.archlinux.org/man/paccache.8) script, provided by the [`pacman-contrib`](https://archlinux.org/packages/?name=pacman-contrib) package. By default, it removes old cached versions of both installed and uninstalled packages, keeping only the **three most recent versions**:

```
paccache -r
```

If you want to automate the cleanup, you can enable and start the `paccache.timer` systemd unit to **run weekly** and discard unused packages automatically:

```
systemctl enable --now paccache.timer
```
