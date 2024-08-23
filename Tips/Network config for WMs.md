After installation, you should start/enable NetworkManager.service and disable iwd.service (or any other service that wants to configure the network, in order to avoid conflict).

It's a good idea to add ``nm-applet``` to your autostart. It will make a icon appear in your tray and will enable you to configure your network using a graphical interface.

NetworkManager comes with nmcli (command line) and nmtui (graphical interface).

## nmcli usage examples:

**List nearby Wi-Fi networks:**

nmcli device wifi list

**Connect to a Wi-Fi network:**

nmcli device wifi connect *SSID_or_BSSID* password *password*

