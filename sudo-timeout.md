# Change the default sudo timeout on Linux

```
sudo visudo
```

OR

```
sudo micro /etc/sudoers
```

```
Defaults    timestamp_timeout=60  #60 min
```

# SPECIFIC USER

```
Defaults:USER timestamp_timeout=0
```

