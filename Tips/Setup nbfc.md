Install `nbfc-linux` from the AUR. Although its not the original implementation, it offers several advantages over it. Thats why I strongly recommend `nbfc-linux` over the `nbfc` package.

Update to the latest configuration files:

``` 
sudo nbfc update
```

Attempt to automatically apply a suitable configuration:

```
sudo nbfc config --set auto
```

If automatic detection fails, identify your notebook model:

```
sudo dmidecode -s system-product-name
```

List the recommended configurations and select the one that most closely matches your model:

```
nbfc config --recommend
```

Manually set the chosen configuration. For example:

```
sudo nbfc config --set "Acer Nitro AN515-57"
```

Enable the NBFC service to start automatically at boot:

```
sudo systemctl enable nbfc_service
```

Start the service:

```
nbfc start
```

To manually force a specific fan speed, use:

```
nbfc set -s <PERCENTAGE>
```
