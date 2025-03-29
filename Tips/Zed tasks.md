ZED_FILE: absolute path of the currently opened file (e.g. /Users/my-user/path/to/project/src/main.rs)
ZED_FILENAME: filename of the currently opened file (e.g. main.rs)
ZED_DIRNAME: absolute path of the currently opened file with file name stripped (e.g. /Users/my-user/path/to/project/src)

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

cd $1

echo ""

case "$2" in
    *.c) clang -o "${2%.c}" $3 && ./"${2%.c}";;
    *.py) python $3 ;;
esac

echo ""
```
