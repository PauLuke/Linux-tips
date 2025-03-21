# Running Code in the Terminal with Geany

To make Geany run your code in a terminal, you'll need to configure the "Terminal" setting in Geany's preferences. Here's how to do it:

## 1. Open Geany Preferences

In Geany's top menu bar, click on **Edit > Preferences > Tools**. There you will find the **Terminal** option that needs to be configured.

## 2. What to Put in the "Terminal" Setting

You need to tell Geany which command it should use to run your program in a terminal. For example:

```
kitty --hold sh -c "chmod +x %c && %c"
```

## 3. Explanation of the Command

- `kitty` is the terminal emulator I've chosen to run the program. You can replace it with any other terminal you prefer (e.g., `alacritty`, `foot`, `xterm`, etc.), just make sure how it handles command executions.
- `--hold` prevents kitty from closing immediately after executing the program. If you are using any other terminal, this flag probably will cause a error.
- `sh` is the shell used to run the following command. You can replace it with any other shell you prefer (e.g., `bash`, `zsh`, `fish`, etc.).
- `-c` tells the shell to execute the command that follows.
- `chmod +x %c && %c` makes the compiled file executable and then runs it. `%c` is a placeholder Geany will substitutes with a shell script file that will make your code run.

## 4. Why `chmod +x %c`?

Sometimes, the script file that Geany generates isn't marked as executable by default. This can result in an error when the shell tries to execute it. Adding chmod +x %c ensures the file is executable before attempting to run it. This small fix can save you from confusing runtime errors.
