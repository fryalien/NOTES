# MAGNET FILE ASSOCIATION LINUX MINT

Check current default:

```
xdg-mime query default x-scheme-handler/magnet 
```

to see which app is currently set.

Set a new default (e.g., qBittorrent):

```
xdg-mime default org.qbittorrent.qBittorrent.desktop x-scheme-handler/magnet
```

Replace org.qbittorrent.qBittorrent.desktop with the .desktop file of your preferred client (e.g., transmission.desktop for Transmission).

For other clients, find the correct .desktop file using:

```
find /usr/share/applications -name "*.desktop" | grep -i "qbittorrent\|transmission\|deluge"
```
