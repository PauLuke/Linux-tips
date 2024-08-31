Use [feh](https://wiki.archlinux.org/title/Feh) or any other similar program.

How it works:

1. Add the following to your i3 *config* file:
```
exec_always --no-startup-id feh --bg-fill ~/.config/i3/background
```
Obs.: Besides "--bg-fill" you can use other scaling options as:
```
--bg-tile FILE
--bg-center FILE
--bg-max FILE
```
