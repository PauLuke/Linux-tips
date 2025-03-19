# Setting a Flatpak Browser as Your Default in Linux

If you're using a browser installed via Flatpak and want to set it as your default browser, here's how you can do it:

## 1. Locate the .desktop file of your browser:

  Flatpak stores .desktop launcher files in specific directories. On most systems, you’ll find them here:
```
/var/lib/flatpak/exports/share/applications/
```

(If you’re on a single-user setup, also check: `~/.local/share/flatpak/exports/share/applications/`)

## 2. Find your browser’s .desktop file:

  Look for the file that corresponds to your browser, such as org.mozilla.firefox.desktop or similar.

## 3. Set it as the default browser:

  From the directory where your browser’s .desktop file is located, run the following command, replacing the filename with the actual name of your browser’s .desktop file:
```
xdg-settings set default-web-browser [your_flatpak_browser.desktop]
```
## 4. Make sure it worked:

That’s it! Your Flatpak browser should now be set as the system default, but to make sure it worked, run:
```
xdg-settings get default-web-browser
```

It should return your browser’s .desktop file.
