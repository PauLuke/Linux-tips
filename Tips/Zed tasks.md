I started relearning C after a long time afar from the language. I didn't wanted to do what I did back then when I manualy compiled and ran my code every time, so I begin looking for a way to do this automaticaly. I found that the solution in Zed is to create a task, which is basically a command, and run it trough a keybiding. He is the actual explanation of what a task is (from Zed's website):

> Zed supports ways to spawn (and rerun) commands using its integrated terminal to output the results. These commands can read a limited subset of Zed state (such as a path to the file currently being edited or selected text).

Here are some examples of the Zed states you can use:

- **ZED_FILE:** absolute path of the currently opened file (e.g. /Users/my-user/path/to/project/src/main.rs)
- **ZED_FILENAME:** filename of the currently opened file (e.g. main.rs)
- **ZED_DIRNAME:** absolute path of the currently opened file with file name stripped (e.g. /Users/my-user/path/to/project/src)

~/.config/zed/keymap.json

```
{
    "context": "Workspace",
    "bindings": {
      // "shift shift": "file_finder::Toggle"
      "ctrl-t": "terminal_panel::ToggleFocus",
      "alt-g": ["task::Spawn", { "task_name": "run" }]
    }
  },
```

~/.config/zed/tasks.json

```
[
	{
		"label": "run",
		"command": "~/scripts/run.sh $ZED_DIRNAME $ZED_FILENAME $ZED_FILE"
	}
]
```

Script

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

## Credits
[Zed article on tasks](https://zed.dev/docs/tasks)
