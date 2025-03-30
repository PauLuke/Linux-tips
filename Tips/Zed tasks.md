I started relearning C after a long time afar from the language. I didn't wanted to do what I did back then when I manualy compiled and ran my code every time, so I begin looking for a way to automaticaly do this for me. I found that the solution in Zed is to create a task and run it trough a keybing. 

Zed supports ways to spawn (and rerun) commands using its integrated terminal to output the results. These commands can read a limited subset of Zed state (such as a path to the file currently being edited or selected text).

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

## Credits
[Zed article on tasks](https://zed.dev/docs/tasks)
