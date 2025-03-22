# GTK dark mode

To change the light/dark mode, you have to change the used theme. 

## Basic theme configuration:

To switch themes instantly for running programs we will use **gsettings**. For desktops running with Wayland, **gsettings** is queried. To query **gsettings** configuration, GTK requires the Settings XDG Desktop Portal, provided by `xdg-desktop-portal-gtk`, to be running. So you may need to install this packge. 

To discover the current GTK theme:

```
$ gsettings get org.gnome.desktop.interface gtk-theme
```

To set a GTK 3 theme, use:

```
gsettings set org.gnome.desktop.interface gtk-theme theme_name
```

For example, if you want to use Adwaita-dark do:

```
gsettings set org.gnome.desktop.interface gtk-theme Adwaita-dark
```

For GTK 4, use: 

```
gsettings set org.gnome.desktop.interface color-scheme "prefer-dark"
```

##  Additinal resources:

Additionally, you can also change the icons with **gsettings**

```
gsettings set org.gnome.desktop.interface icon-theme icon_theme_name
```

For example, if you want to use Adwaita icons do:

```
gsettings set org.gnome.desktop.interface icon-theme Adwaita
```


For users who prefer a graphical interface, you can use the `gnome-tweaks` tool. Install it with your package manager and launch it to change themes, icon packs, fonts, and other desktop appearance settings.

## Credits:

(Arch Wiki: Dark mode switching)[https://wiki.archlinux.org/title/Dark_mode_switching]

(Arch Wiki: GTK)[https://wiki.archlinux.org/title/GTK#Configuration]

(Github discussion)[https://github.com/hyprwm/Hyprland/discussions/5867]


