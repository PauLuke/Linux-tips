1. Enter in the input group executing the following command:

```
sudo gpasswd -a $USER input
```

2. Install Fusuma from AUR:

```
yay -S ruby-fusuma
```

3. Add the followig to your wm config file:

```
# TODO: Move to autostart
# To ensure that no multiple instances of fusuma are started, was previously an issue

exec_always --no-startup-id sh -c "pkill fusuma; fusuma -d"
```
