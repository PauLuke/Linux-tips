The following is from the Arch Wiki:

Pacman stores its downloaded packages in /var/cache/pacman/pkg/ and does not remove the old or uninstalled versions automatically. This has some advantages:

1. It allows to downgrade a package without the need to retrieve the previous version through other means, such as the Arch Linux Archive.
2. A package that has been uninstalled can easily be reinstalled directly from the cache directory, not requiring a new download from the repository.

However, it is necessary to deliberately clean up the cache periodically to prevent the directory to grow indefinitely in size.

The [paccache](https://man.archlinux.org/man/paccache.8) script, provided within the [pacman-contrib](https://archlinux.org/packages/?name=pacman-contrib) package, deletes all cached versions of installed and uninstalled packages, except for the most recent three, by default:

`# paccache -r`

Enable and start paccache.timer to discard unused packages weekly. 
