## 1. Install dark themes

Make sure you have a dark theme installed on your system. I suggest the istallation of `gnome-themes-extra` and `gnome-themes-extra-gtk2` for GTK applications and `adwaita-qt5-git` and `adwaita-qt6-git` for QT application.

## 2. Verify portal existence

Make sure the portal that tells libadwaita apps about the color scheme is installed:

```
sudo pacman -S xdg-desktop-portal-gnome
```

## 3. Change theme and prefer dark

Install `nwg-look`. Inside it, select adwaita-dark as your theme and mark "prefer dark" on.
