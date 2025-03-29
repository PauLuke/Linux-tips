# Theming Gedit

I'm a big fan of the Dracula theme, and whenever I want to use it in a new application, I check their website for installation instructions. They usually do a great job explaining how to apply the theme. However, when I tried theming Gedit, things didn’t go as expected.

The official instructions suggest downloading the raw .xml file and placing it in $HOME/.local/share/gedit/styles/. But on Arch Linux, this had no effect—the theme simply didn’t appear in Gedit's preferences.

After searching the internet for a solution, I found the answer on Reddit. Here’s what you need to do:

## 1. Download the theme:

If your version of Gedit is **46 or newer**, use the following command:

```
wget https://raw.githubusercontent.com/dracula/gedit/master/dracula-46.xml -O dracula.xml
```

⚠️ If you have an **older version** of Gedit, use this command instead:

```
wget https://raw.githubusercontent.com/dracula/gedit/master/dracula.xml
```

## 2. Place the theme in the correct directory:

Instead of the official directory mentioned in the Dracula documentation, the location that worked for me on Arch Linux is `~/.local/share/libgedit-gtksourceview-300/styles/`.
To create this directory if it doesn't exist, run:

```
mkdir -p ~/.local/share/libgedit-gtksourceview-300/styles/
```

Then, move the downloaded theme file into this folder.

## Credits:
Thanks to [ManlyMaid on Reddit](https://www.reddit.com/r/linux4noobs/comments/1dxamfo/comment/ldr941h/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button) for the solution.

