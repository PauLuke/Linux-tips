# Enable swipe gestures in Brave

Swipe gestures to navigate back and forward in tab history are not enabled by default in Brave, and there is no option to enable them through the browser’s interface.
To enable this feature, you need to manually edit Brave’s desktop entry.

## 1. Open the file located at:
```
/usr/share/applications/brave-browser.desktop
```

## 2. Find the line that starts with Exec= and add the following flag to the command:
```
--enable-features=TouchpadOverscrollHistoryNavigation
```

For example, the line might look like this after editing:
```
Exec=brave --enable-features=TouchpadOverscrollHistoryNavigation %U
```

This change will ensure that swipe gestures work whenever you launch Brave from the system menu or application launcher.
