**Description:** How to install and enable Ly

1. Clone the repository

```
git clone --recurse-submodules https://github.com/nullgemm/ly.git
```

2. Enter the ly directory

```
cd ly
```

3. Compile

```
make
```

4. Install Ly and the provided systemd service file

```
sudo make install
```

5. Disabe the old display manager (ex.)

```
systemctl disable gdm
```

6. Enable the service

```
sudo systemctl enable ly.service
```