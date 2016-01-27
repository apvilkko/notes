# ffmpeg: convert SBS 3D to anaglyph

```
ffmpeg -i in.mp4 [-ss 00:01:30.0] -vf stereo3d=sbs2l:arcc -acodec copy -b:v 3000k [-preset ultrafast] -vcodec libx264 [-t 10] out.mp4
```
