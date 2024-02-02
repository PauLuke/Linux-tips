##### What to install
1. Install pip

```
yay -S python-pip
```

3. Install nautilus-open-any-terminal e python-nautilus

```
yay -S nautilus-open-any-terminal python-nautilus
```

4. With pip install nautilus-open-any-terminal

```
pip install nautilus-open-any-terminal
```

##### What to do after

```
glib-compile-schemas /usr/share/glib-2.0/schemas
```

```
gsettings set com.github.stunkymonkey.nautilus-open-any-terminal terminal TERMINAL_NAME
```

##### Relevant texts

[nautilus-open-any-terminal documentation](https://github.com/Stunkymonkey/nautilus-open-any-terminal)
