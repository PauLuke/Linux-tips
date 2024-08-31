To easily have control upon your CPU governor you can install the *cpupower* package. The package is not required to use scaling, but is highly recommended because it provides useful command-line utilities and a systemd service to change the governor at boot. 

To install the *cpupower* package you can run:
```
# pacman -S cpupower
```

Here is a example of how to define the governor of all cores of your CPU to *powersave* governor:
```
sudo cpupower -c all frequency-set -g powersave
```
