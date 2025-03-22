# GTK dark mode

To change the light/dark mode, you have to change the used theme. 

# 1. Basic theme configuration:

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

Additionally, you can also change the icons with **gsettings**

```
gsettings set org.gnome.desktop.interface icon-theme icon_theme_name
```

For example, if you want to use Adwaita icons do:

```
gsettings set org.gnome.desktop.interface icon-theme Adwaita
```

For a graphical configurantion, you can use the `gnome-tweaks`package.
