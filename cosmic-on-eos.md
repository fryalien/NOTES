**COMSMIC ON EOS**

>INSTALL LINK

https://github.com/EndeavourOS-Community-Editions/cosmic

---

>With cosmic-greeter

```
wget -qN --show-progress -O /home/liveuser/user_pkglist.txt https://raw.githubusercontent.com/EndeavourOS-Community-Editions/cosmic/main/user_pkglist.txt
```

>Change systemd services module to enable cosmic-greeter

```
sudo wget -qN --show-progress -O /etc/calamares/modules/services-systemd.conf https://raw.githubusercontent.com/EndeavourOS-Community-Editions/cosmic/main/services-systemd.conf
```

---

>App center issues

```
sudo pacman -S packagekit
```

>Missing Power & Battery settings

```
sudo pacman -S power-profiles-daemon   
```

---

>Catppuccin theme

```
cd Public; git clone https://github.com/catppuccin/cosmic-desktop.git
```
