How to use an appimage as a native program?  

Actually, there is at least two ways of doing that. The easy one is simply installing [AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher) and then opening the intended appimage file. Doing that you will automatically be asked to integrate the appimage in your system.  

1) Create a folder in `~/.local/share/applications/` for the appimage:  

`mkdir ~/.local/share/applications/appimages`

2) Create a folder in ~/.local/share/applications/appimage/ for the icons:

`mkdir ~/.local/share/applications/appimages/icons`

3) Put the appimage in that folder:

`mv ~/.local/share/applications/appimages/appimage_name`

4) Create a ".desktop" file at `~/.local/share/applications`:

```
cd ~/.local/share/applications && touch appimage_name.desktop
```

5) Edit the created file putting the text bellow:

```
[Desktop Entry]

# The type as listed above
Type=Application

# The name of the application
Name=program_name

# The path to the image you want to use as icon
Icon=~/.local/share/applications/appimages/icons/icon_name
```

6) Update de database:

```
update-desktop-database ~/.local/share/applications
```

