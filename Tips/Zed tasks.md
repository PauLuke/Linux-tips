# Zed tasks

## The Problem

Nowadays, I'm relearning C. When I first learned it, I remember having to manually compile and run my code every time. This became tedious over time, so I decided to look for a way to automate the process. Currently, I'm using Zed as my editor, and I found that the best solution is to create a task—essentially a command that Zed can execute, triggered by a keybinding.

---
Here’s how Zed describes tasks:

> Zed supports ways to spawn (and rerun) commands using its integrated terminal to output the results. These commands can read a limited subset of Zed state (such as a path to the file currently being edited or selected text).

Here are some examples of the Zed states you can use:

- **ZED_FILE:** absolute path of the currently opened file (e.g. `/Users/my-user/path/to/project/src/main.rs`)
- **ZED_FILENAME:** filename of the currently opened file (e.g. `main.rs`)
- **ZED_DIRNAME:** absolute path of the currently opened file with file name stripped (e.g. `/Users/my-user/path/to/project/src`)
---

## The solution 

I decided I would setup something that would allow me to run code in any programming language I use, not just C. So I created a shell script that takes Zed’s state variables as arguments and executes the appropriate command based on the file type.

Here’s the script:

```
#!/bin/bash

# Change to the specified directory
cd "$1" || { echo "Failed to change directory to $1"; exit 1; }

echo ""

# Ensure a file argument is provided
if [ -z "$2" ]; then
    echo "Error: No file specified."
    exit 1
fi

case "$2" in
    *.c) 
        executable="${2%.c}"
        clang -o "$executable" "$2" $3 && "./$executable";;
    *.py) 
        python "$2" $3;;
    *) 
        echo "Error: Unsupported file type.";;
esac

echo ""
```
Next, I needed to integrate this script into Zed. I created a `task.json` file in `~/.config/zed/` with the following content:

```
[
  {
    "label": "run",
    "command": "~/scripts/run.sh $ZED_DIRNAME $ZED_FILENAME $ZED_FILE"
    }
]
```

Then, I added a keybinding in my `keymap.json` file to execute the task when pressing `Alt+G`:

```
{
    "context": "Workspace",
    "bindings": {
        "ctrl-t": "terminal_panel::ToggleFocus",
        "alt-g": ["task::Spawn", { "task_name": "run" }]
    }
}
```

## Conclusion

With this setup, I can now run my code effortlessly with a single keypress in Zed, without manually compiling and executing files. This approach can easily be extended to support more languages by modifying the shell script


## Credits
[Zed article on tasks](https://zed.dev/docs/tasks)
