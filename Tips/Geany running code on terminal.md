# Geany running code on terminal

To make Geany run your code on terminal, you have to configure  the "Terminal" setting in Geany's preferences. Here's how you can do that:

## 1. Find where the preferences are:

In Geany's top bar you should see a "Edit" option. Go to Edit > Preferences > Tools. There you should be able to see the "Terminal" option you will have to change.

## 2. What to put in the "Terminal" setting?

You will give to Geany the command it should use to run your programm on the terminal. In my case it is:

```
kitty --hold sh -c "chmod +x %c && %c"
```
## 3. explaining the command:

- `kitty` is the terminal emulator I chouse to run my program
- `--hold` is a flag that basically prevents kitty of closing immediately after executing the programm
- `sh` is the shell I'm using to run the command that will follow. You can change to whatever shell you want (bash, zsh, fish, ...)
- `-c` is a 
