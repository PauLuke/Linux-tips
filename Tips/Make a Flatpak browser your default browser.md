First, you have to find where Flatpak is storing the .desktop files of your programms. In my case (I use Arch BTW) these files are located in `/var/lib/flatpak/exports/share/applications/`.
Now, inside the folder where the .desktop file of my browser is located I run the following command: `xdg-settings set default-web-browser [your_flatpak_browser.desktop]`.
To verify if it worked run `xdg-settings get default-web-browser`.
