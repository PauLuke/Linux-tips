Following the [Arch Wiki](https://wiki.archlinux.org/title/Dark_mode_switching):

1. Install gnome-themes-extra, adwaita-qt5-git (AUR) and adwaita-qt6-git (AUR);
2. Export GTK_THEME=Adwaita:dark, GTK2_RC_FILES=/usr/share/themes/Adwaita-dark/gtk-2.0/gtkrc and QT_STYLE_OVERRIDE=Adwaita-Dark. One way to accomplish this is by modifying your .profile file ([see more about this](https://www.ibm.com/docs/en/aix/7.2?topic=files-profile-file)) adding the following:

```
  export GTK_THEME=Adwaita:dark
  export GTK2_RC_FILES=/usr/share/themes/Adwaita-dark/gtk-2.0/gtkrc
  export QT_STYLE_OVERRIDE=Adwaita-Dark
```
