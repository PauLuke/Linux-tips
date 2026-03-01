## For X11:

Create `~/.Xresources` with the following:

```
Xcursor.theme: <cursor theme>
Xcursor.size: <size>
```

Run:

```
xrdb ~/.Xresources
```

You can also create `~/.xprofile` with the following:

```
xrdb ~/.Xresources
```

## For Wayland:

Download `nwg-look` to manage GTK and cursor theming.
