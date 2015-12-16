# sox: Create mp3 preview snippets with auto fades

```
sox infile.wav -C 320.01 outfile.mp3 trim 2:40.0 120 fade h 0:5 0 0:5
```

# ffmpeg: get audio stream from video without re-encoding

```
ffmpeg -i input.mp4 -vn -acodec copy output.aac
```

# ffmpeg: get part of audio file

```
ffmpeg -ss 0 -i input.wav -t 30 output.wav
```
 * ss = where to start (seconds)
 * t = how many seconds
