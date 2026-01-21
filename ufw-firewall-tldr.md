>Backup.

```
cd ~/Documents
```

```
sudo cp /etc/ufw/user.rules ~/Documents/user.rules
```

```
sudo cp /etc/ufw/user6.rules ~/Documents/user6.rules
```

>Restore.

```
cd ~/Documents
```

```
sudo ufw disable
```

```
sudo cp -fv user.rules /etc/ufw/
```

```
sudo cp -fv user6.rules /etc/ufw/
```

```
sudo ufw enable
```
