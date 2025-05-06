# Notify when a password is required in yay

To make your terminal emit a bell sound whenever *sudo* prompts for a password during *yay* operations, run:
```
yay -Y --sudoflags "-B" --save
```

This command tells *yay* to pass the `-B` flag to *sudo*, which triggers an audible bell when a password is requested.

## What This Does

Running `yay --save` creates a default configuration file if one doesn’t already exist. This file is typically located at:
```
~/.config/yay/config.json
```

It stores your chosen flags in the config file, so you don’t have to set them every time.
