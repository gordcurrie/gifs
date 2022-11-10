# Get window info

`xwininfo``

# Capture window

`ffmpeg -f x11grab -y -r 30 -s 963x588 -i :1+279,120 -vcodec huffyuv out.avi`

# Convert capture to gif

```
ffmpeg -ss 3 -t 20 -i out.avi -filter_complex [0:v] palettegen palette.png
ffmpeg -ss 3 -t 20 -i out.avi -i palette.png -filter_complex [0:v][1:v] paletteuse out.gif
```
