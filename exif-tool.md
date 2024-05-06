# REMOVE METADATA FROM YOUR PHOTOS


YOUTUBE: https://youtu.be/V7z4VQcVx0s

**INSTALL EXIFTOOL**

```
sudo pacman -S perl-image-exiftool
```

```
sudo dnf install perl-image-exiftool
```



**REMOVE METADATA AND EXIF DATA FROM PHOTO**
```
exiftool -All= image_name.jpg
```

**REMOVE METADATA AND EXIF DATA FROM WHOLE FOLDER**
```
exiftool -All= *
```

**REMOVE ONLY EXIF DATA**
```
exiftool -EXIF= image_name.jpg
```

**REMOVE METADATA AND EXIF DATA AND REWRITING ORIGINAL FROM WHOLE FOLDER**
```
exiftool -overwrite_original -All= *
```

**REMOVE METADATA AND EXIF DATA AND REWRITING ORIGINAL FROM PHOTO**
```
exiftool -overwrite_original -All= image_name.jpg
```
