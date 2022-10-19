# Video

## Convert SBS 3D to anaglyph with ffmpeg

```
ffmpeg -i in.mp4 [-ss 00:01:30.0] -vf stereo3d=sbs2l:arcc -acodec copy -b:v 3000k [-preset ultrafast] -vcodec libx264 [-t 10] out.mp4
```

## Retime 24fps video to fit 25fps PAL audio without re-encoding (ffmpeg)

Use case: PAL DVD with desired audio track and a 24 fps version of the same thing (e.g. BluRay).

Here `movie.mkv` is the PAL version, `movie.mp4` is the BluRay version, assumed encoded with h265.

Extract audio stream from 25 fps version (select correct language with map, here the index 2 is used):

```
ffmpeg -y -i movie.mkv -c:a copy -map 0:a:2 audio.mka
```

Extract h265 video stream from 24 fps version:

```
ffmpeg -y -i movie.mp4 -c:v copy -bsf hevc_mp4toannexb -f hevc video.h265
```

Generate timestamps (retime to 25 fps):

```
ffmpeg -fflags +genpts -r 25 -i video.h265 -vcodec copy video.mp4
```

Mux the retimed video with audio:

```
ffmpeg -itsoffset 1.057 -i video.mp4 -i audio.mka -c copy output.mp4
```

If audio is not in sync, use `itsoffset` with delay in seconds (here e.g. 1.057 seconds; position matters, if the delay goes the wrong way move `itsoffset` parameter before the other `-i` switch):

```
ffmpeg -itsoffset 1.057 -i video.mp4 -i audio.mka -c copy output.mp4
```

```
ffmpeg -i video.mp4 -itsoffset 1.057 -i audio.mka -c copy output.mp4
```
