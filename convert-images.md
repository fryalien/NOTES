**ImageMagick packge needs to be installed**

This converts all those formats to png, leaving copy of original photo.

```
mogrify -format png *.jpg
```

```
mogrify -format png *.jpeg
```

```
mogrify -format png *.bmp
```

**CONVERT WITH BIGGER QUALITY (default 92)**

```
convert wallpaper.png -quality 100 wallpaper.jpg
```

**RESIZE IMAGE - preserve aspect ratio**

```
convert example.png -resize 1920x1080 example.png
```

**RESIZE IMAGE - ignore aspect ratio**

```
convert wallpaper.png -resize 200x100! wallpaper.png
```

**ROTATE AN IMAGE by 90 degrees**

```
convert wallpaper.jpg -rotate 90 wallpaper-rotated.jpg
```

**MULTIPLE ROTATE**

```
for file in *.png; do convert $file -rotate 90 rotated-$file; done
```