## 1. Making the entry

Desktop entries for applications are basically comprised of a path to an executable with some metadata.
They must have a type and contain at least a name and executable location.

Here is a basic template:

```
[Desktop Entry]
Type=Application
Name=someApp
Exec=someApp
Icon=someApp
```

You should save the .desktop file to `~/.local/share/applications/`.

## 2. Icons

On `~/.local/share/icons/hicolor/` you will see folders named like 48x48, 64x64, 128x128, 256x256... Inside each one of these folders there is a folder called "apps". Choose one of these folders and put your icon.
