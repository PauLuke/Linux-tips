If you are having trouble intalling Katrain from the AUR package do the following:

1. Install *python-pipx*

```
sudo pacman -S python-pipx
```

2. Install Katrain through pipx

```
pipx install katrain
```

You can also make Katrain a desktop application:

1. Create a .desktop file for Katrain in `/usr/share/applications/` with the following content:

```
[Desktop Entry]
Name=Katrain
GenericName=SGF Editor (Go)
Comment=A tool for analyzing games and playing go with AI feedback from KataGo.
Exec=/home/pauluke/.local/bin/katrain
Terminal=false
Type=Application
Icon=/usr/share/icons/katrain.png
Categories=Game;
MimeType=application/x-go-sgf;
```
Notice that it is defining a icon located in `/usr/share/icons/`. Make sure you placed the icon file with the correct name in there.
