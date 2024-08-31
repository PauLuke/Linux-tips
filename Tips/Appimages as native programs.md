How to use an appimage as a native program?  

Actually, there are at least two ways to do this. The easiest one is to installing [AppImageLauncher](https://github.com/TheAssassin/AppImageLauncher) and let it handle all the work. When you execute a *appimage* file, *AppImageLauncher* will automatically ask you to integrate this *appimage* to your system. That's it.

But if you like to make things manually, follow the process bellow:

1) I recommend creating a dedicated folder to store your AppImages. This will help keep everything organized in one place. This is a example of what you can do:

`mkdir ~/.local/share/applications/appimages/`

2) I also suggest creating a folder for the icons you'll use:

`mkdir ~/.local/share/applications/appimages/icons/`

3) You can now place your AppImages in the folder you created:

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

