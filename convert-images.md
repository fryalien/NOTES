**ImageMagick needs to be installed**

This magicks all those formats to png, leaving copy of original photo.

```
mogrify -format png *.jpg
```

```
mogrify -format png *.jpeg
```

```
mogrify -format png *.bmp
```

**magick WITH BIGGER QUALITY (default 92)**

```
magick wallpaper.png -quality 100 wallpaper.jpg
```

**RESIZE IMAGE - preserve aspect ratio**

```
magick example.png -resize 1920x1080 example.png
```

**RESIZE IMAGE - ignore aspect ratio**

```
magick wallpaper.png -resize 1920x1080! wallpaper.png
```

**ROTATE AN IMAGE by 90 degrees**

```
magick wallpaper.jpg -rotate 90 wallpaper-rotated.jpg
```

**MULTIPLE ROTATE**

```
for file in *.png; do magick $file -rotate 90 rotated-$file; done
```