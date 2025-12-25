From the AUR install `nbfc-linux`.

Download the latest configuration files from the internet:

``` 
sudo nbfc update
```

Try to find a configuration automatically:

```
sudo nbfc config --set auto
```

If the previous command didn't work, list the recommended option:

```
nbfc config --recommend
```

Then, load a configuration. For example:

```
sudo nbfc config --set "Acer Nitro AN515-57"
```

Now start the service:

```
nbfc start
```

If you want to force a especific fan speed use:

```
nbfc set -s <PERCENTAGE>
```
