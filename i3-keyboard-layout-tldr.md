**change keyboard layout in i3 (no keyboard layout shown on the bar)**

>setxkbmap needs to be installed

```
micro ~/.config/i3/config
```

>add this line to change with `alt shift`

```
# set KEYBOARD layout
exec --no-startup-id setxkbmap -layout 'us,hr' -option 'grp:alt_shift_toggle'
```

---

**change different keyboard variants**

```
setxkbmap us -variant dvorak
```

---

**change keyboard layout in i3 (keyboard layout shown on the bar, only on the left side)**

>download `i3-keyboard-layout` to `~/.config/i3/` folder

LINK: https://github.com/porras/i3-keyboard-layout

>make the file executable

```
chmod +x ~/.config/i3/i3-keyboard-layout
```

>install i3bar

```
sudo dnf install i3bar
```

>add this lines to i3 config file

```
micro ~/.config/i3/config
```

# set KEYBOARD layout

```
bindsym control+Shift+x exec ~/.config/i3/i3-keyboard-layout cycle us hr
```

>under bar add these lines

```
bar {

    status_command i3status -c ~/.config/i3/i3status.conf | ~/.config/i3/i3-keyboard-layout i3status -c /~/.config/i3/i3status.conf
}
```

>in `i3status.conf` under `general` add

```
micro ~/.config/i3/i3status.conf
```

```
general {
        ...
        ...
        output_format = i3bar
}

```

---

**list available locales**

```
localectl list-x11-keymap-layouts
```

**list available variants**

```
localectl list-x11-keymap-variants
```

---

**locale settings**

```
localectl status
```
