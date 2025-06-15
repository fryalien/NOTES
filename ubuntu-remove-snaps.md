**HOW TO REMOVE SNAPS FROM UBUNTU**

>Shut the snapd service.

```
sudo systemctl stop snapd
```

>Check the procesess.

```
ps -ef | grep snap
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

>Remove root snap folder.

```
sudo rm -rf /root/snap/
```

>Look for leftover direcory (and delete if anything is left).

```
sudo find / -type d -name snap

```

>Stop snaps being reinstalled.

```
sudo micro /etc/apt/preferences.d/nosnap.pref
```

>Add folowing lines.

```
Package: snapd
Pin: release a=*
Pin-Priority: -10
```

---

reinstall snaps later

```
sudo apt install snapd
```

---

**INSTALL FLATPAK**

```
sudo apt install flatpak gnome-software-plugin-flatpak
```

```
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```
