X11 provides configurations in a directory “X11/xorg.conf.d/” this directory could live in various places on your system depending on your distribution.

However, X11 will always attempt to also load configurations from /etc/X11/xorg.conf.d/ when present.

To ensure the directory exists, run:

```
sudo mkdir -p /etc/X11/xorg.conf.d
```

Next we’ll create a new file “90-touchpad.conf”. The configuration file names end with .conf and are read in ASCII order—by convention file names begin with two digits followed by a dash.

```
sudo touch /etc/X11/xorg.conf.d/90-touchpad.conf
```

Now open up the file your editor of choice (with suitable write permission of course) and paste the following:

```
Section "InputClass"
        Identifier "touchpad"
        MatchIsTouchpad "on"
        Driver "libinput"
        Option "Tapping" "on"
        Option "TappingButtonMap" "lrm"
        Option "NaturalScrolling" "on"
        Option "ScrollMethod" "twofinger"
EndSection
```

or a more simple one:

```
Section "InputClass"
        Identifier "touchpad"
        MatchIsTouchpad "on"
        Driver "libinput"
        Option "Tapping" "on"
EndSection
```

