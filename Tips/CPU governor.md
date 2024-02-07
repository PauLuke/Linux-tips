1. Install the following package

```
paru -S cpupower
```

2. Use the command to define the governor of all cores to power save:

```
sudo cpupower -c all frequency-set -g powersave
```
