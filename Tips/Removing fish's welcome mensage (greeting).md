# Removing fish's welcome mensage

The fish shell has a builtin function called "fish_greeting" that is reponsable for prompt the user with a greeting message every time he opens the terminal. In order to change that we should edit the function, so type:
```
function fish_greeting
```

Now we have to writte a command inside that function, but as we want this function to do nothing, we will only type "end" and press `ENTER`:
```
end
```

Finally, we just save the function to never see that greeting message ever again:
```
funcsave fish_greeting
```
