# Easily kill processes in Linux

*pkill* is a command-line tool that lets you terminate processes by their name, providing a convenient alternative to manually locating process IDs and then using *kill* to end them.

## 1. Basic Usage

The simplest way to use `pkill` is to specify the name of the program you want to terminate:

```
pkill firefox
```

This sends the default signal (`SIGTERM`) to all processes named "firefox", asking them to exit.

## 2. Common Options

`pkill` offers several options on how to terminate processes. For example, you can use the `-<signal>` option to specify which signal to send to the process. Common signals include:

- `-15` (SIGTERM): Polite request to terminate (default, allows cleanup).
- `-9` (SIGKILL): Forcefully kill the process (no cleanup, use cautiously).
  
Example:

```
pkill -9 firefox
```

This forcefully kills all firefox processes.

## 3. Verify the Process is Terminated

After running `pkill`, check if the process is gone:

```
pgrep firefox
```

If no output appears, the process was successfully terminated.

## 5. Tips and Cautions

- **Be Precise**: `pkill` can match multiple processes if the name is generic (e.g., `pkill kitty` will kill all instances off "kitty"). So, check with `pgrep -l <name>` to see which processes will be affected first.
- **Avoid SIGKILL (-9)**: Only use `-9` if `pkill <name>` fails, as it prevents processes from saving data or cleaning up.
