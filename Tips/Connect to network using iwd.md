# Connect to network using iwd

*iwd* (iNet wireless daemon) is a wireless daemon for Linux written by Intel. The *iwd* package provides the client program *iwctl*, the daemon *iwd* and the Wi-Fi monitoring tool *iwmon*. 

## 1. Open a interactive prompt of iwd:
To get an interactive prompt do:
```
iwctl 
```
The interactive prompt is then displayed with a prefix of `[iwd]#`. 

## 2. Find the name of your wireless device:
First, if you do not know your wireless device name, list all Wi-Fi devices: 
```
device list
```
If the device or its corresponding adapter is turned off, turn it on:
```
device DEVICE_NAME set-property Powered on
```
```
adapter ADAPTER_NAME set-property Powered on
```

## 3. Search for networks:
Then, to initiate a scan for networks (note that this command will not output anything): 
```
station DEVICE_NAME scan
```

## 4. List all networks found:
You can then list all available networks: 
```
station DEVICE_NAME get-networks
```

## 5. Connect to a network
Finally, to connect to a network: 
```
station DEVICE_NAME connect SSID
```
Credits: https://wiki.archlinux.org/title/Iwd
