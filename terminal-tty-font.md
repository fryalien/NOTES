**INSTALL TTY FONTS ON ARCH**

```
sudo pacman -S terminus-font
```

**INSTALL TTY FONTS ON FEDORA**

```
sudo dnf install terminus-font
```

>Fonts location.

```
cd /usr/share/kbd/consolefonts 
```

>Syntax.

```
setfont font_name
```

>Example.

```
setfont ter-132n
```

> bold

```
setfont ter-132b
```

>Back to default font.

```
setfont
```

>Make it default on all ttys.

```
micro /etc/vconsole.conf
```

>Add at the end of the file.

```
FONT=ter-132n
```

>On CachyOS run this command as well if you have systemd-boot

```
sudo mkinitcpio -P
```
