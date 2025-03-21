
1. Install the dark GTK themes:
 
You can find dark GTK themes in `adw-gtk-theme` package

exec = gsettings set org.gnome.desktop.interface gtk-theme "YOUR_DARK_GTK3_THEME"   # for GTK3 apps
exec = gsettings set org.gnome.desktop.interface color-scheme "prefer-dark"   # for GTK4 apps

3. Export GTK_THEME=Adwaita:dark, GTK2_RC_FILES=/usr/share/themes/Adwaita-dark/gtk-2.0/gtkrc and QT_STYLE_OVERRIDE=Adwaita-Dark. One way to accomplish this is by modifying your .profile file ([see more about this](https://www.ibm.com/docs/en/aix/7.2?topic=files-profile-file)) adding the following:

```
  export GTK_THEME=Adwaita:dark
  export GTK2_RC_FILES=/usr/share/themes/Adwaita-dark/gtk-2.0/gtkrc
  export QT_STYLE_OVERRIDE=Adwaita-Dark
```
