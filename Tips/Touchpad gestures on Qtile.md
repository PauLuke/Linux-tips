Install `libinput-gestures` and the gui application called `gestures` to configure it. You will need `wtype` to execute the keybind under Wayland.

I've tried `xdotool` and `ydotool`, but neither of them worked for me. This is how to use `wtype`:

```
wtype -M win -k Right
```
