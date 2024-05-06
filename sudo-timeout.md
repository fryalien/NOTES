**CHANGE THE DEAFULT SUDO TIMEOUT ON LINUX**

```
sudo visudo
```

or

```
sudo micro /etc/sudoers
```

```
Defaults    timestamp_timeout=60  #60 min
```

**SPECIFIC USER**

```
Defaults:USER timestamp_timeout=0
```

