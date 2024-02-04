# Get window info

`xwininfo`

# Capture window

`ffmpeg -f x11grab -y -r 30 -s 963x588 -i :1+279,120 -vcodec huffyuv out.avi`

# Convert capture to gif

```
ffmpeg -ss 3 -t 52 -i out.avi \                                                                                                 17s 10:16:38
    -vf "fps=10,scale=540:-1:flags=lanczos,split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" \
    -loop 0 out.gif
```
https://superuser.com/questions/556029/how-do-i-convert-a-video-to-gif-using-ffmpeg-with-reasonable-quality
