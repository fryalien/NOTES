# Convert 4k to 1080p
```
ffmpeg -i input_file.mp4 -vf scale=1920:1080 -c:a copy output_file.mp4
```

# Convert H.264 to H.265
```
ffmpeg -i input_file.mp4 -c:v libx265 -vtag hvc1 -c:a copy output_file.mp4
```

# Convert 4k(H.264) to 1080p(H.265)
```
ffmpeg -i input_file.mp4 -c:v libx265 -vtag hvc1 -vf scale=1920:1080 -crf 20 -c:a copy  output_file.mp4
```

---

YOUTUBE: https://youtu.be/bicYWSQdK10
