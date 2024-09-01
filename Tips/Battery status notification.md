If you’re not using a full desktop environment, like Gnome or KDE, you might not have a way to alert you when your laptop's battery is low. In that case, you could create your own battery status notification service to solve this problem.

First, you’ll need a script to check your battery status. You can create one yourself or find a suitable o script online.  I recommend using [the script created by Eric Murphy](https://github.com/ericmurphyxyz/dotfiles/blob/master/.local/bin/battery-alert). I encourage you to read the code and understand it rather than just copying and pasting.

Next, you need to run this script regularly to keep track of your battery status. You can use *cronie*, a daemon that executes specified programs at scheduled times, to do this.

Install *cronie*:
```
sudo pacman -S cronie
```
Now you have to create a cronjob. To do that run:
```
crontab -e
```

Obs.: If have the following error, will you need to change your default editor:
```
no crontab for pauluke - using an empty one
/bin/sh: line 1: /usr/bin/vi: No such file or directory
crontab: "/usr/bin/vi" exited with status 127
```
To change your default editor in fish add the following to *~/.config/fish/config.fish*:
```
set -gx EDITOR [your editor]
```
After you run add the following to your file:
```
*/5 * * * * [path to your script]
```

This will execute your script every 5 minutes.

Additional Tips:

Make sure the script is executable. You can set executable permissions using:
```
chmod +x [path to your script]
```
