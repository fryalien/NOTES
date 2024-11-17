#!/bin/sh
export WLR_NO_HARDWARE_CURSORS=1
export WLR_RENDERER_ALLOW_SOFTWARE=1
exec Hyprland


# starthypr.sh


---
>Put in:
`/usr/share/wayland-sessions/hyprland.desktop`

```
Exec=env WLR_NO_HARDWARE_CURSORS=1 Hyprland
```
