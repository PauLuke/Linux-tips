Description: how to use iwd to connect to a network.

1. Open a interactive prompt of iwd:

```
iwctl 
```

2. Find the name of your wireless device:

```
device list
```

3. Search for networks:

```
station DEVICE_NAME scan
```

4. List all networks found:

```
station DEVICE_NAME get-networks
```

5. Connect for a network

```
station DEVICE_NAME connect SSID
```
