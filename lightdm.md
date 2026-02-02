**LIGHTDM**

>Check which dispaly manager is running.

```
systemctl status display-manager
```

or

```
systemctl show display-manager --property=Id
```

or

```
grep 'ExecStart=' /etc/systemd/system/display-manager.service
```

>Config files.

```
micro /etc/lightdm/lightdm.conf
```

```
micro  /etc/lightdm/lightdm-gtk-greeter.conf
```

**SLICK GREETER**

```
micro /etc/lightdm/slick-greeter.conf
```

>GUI

```
yay -S lightdm-settings
```

>START

```
sudo lightdm-settings
```

>INSTALL SLICK GREETER

```
sudo pacman -S lightdm-slick-greeter
```
