How to use an appimage as a native program?  

Actually, there is at least two ways of doing that. The easy one is simply installing [AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher) and then opening the intended appimage file. Doing that you will automatically be asked to integrate the appimage in your system.  

But if you like to make things manually follow the process bellow:

1) I suggest the creation of a folder in `~/.local/share/applications/` for the appimage:  

`mkdir ~/.local/share/applications/appimages/`

2) I also recommend the creation of a folder in `~/.local/share/applications/appimage/` for the icons:

`mkdir ~/.local/share/applications/appimages/icons/`

3) Now put the appimage in the folder designated folder:

`mv ~/.local/share/applications/appimages/ [appimage_path]`

4) Create a ".desktop" file at `~/.local/share/applications/`:

`touch ~/.local/share/applications/[appimage_name.desktop]`

5) Copy and paste the text bellow in the newly created ".desktop" file:

```
[Desktop Entry]

# The type as listed above
Type=Application

# The name of the application
Name=program_name

# The path to the image you want to use as icon
Icon=~/.local/share/applications/appimages/icons/icon_name
```

6) Update the applications database to see the results:

`update-desktop-database ~/.local/share/applications`

