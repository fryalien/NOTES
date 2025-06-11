**HOW TO REMOVE SNAPS FROM UBUNTU**

>Shut the snapd service.

```
sudo systemctl stop snapd
```

>Remove everything installed via snap.

```
sudo apt remove --purge --assume-yes snapd gnome-software-plugin-snap
```

>Remove snap direcotry.

```
rm -rf ~/snap/
```

>Remove snap cache.

```
sudo rm -rf /var/cache/snapd/
```

>Look for leftover direcory (and delete if anything is left).

```
sudo find / -type d -name snap

```

---

reinstall snaps later

```
sudo apt install snapd
```