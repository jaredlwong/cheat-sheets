https://ottverse.com/trim-cut-video-using-start-endtime-reencoding-ffmpeg/

```bash
ffmpeg -ss 0 -t 10 -i bbb_sunflower_2160p_60fps_normal.mp4 -c:v copy -c:a copy bbb_2160p_60fps_10s.mp4
```

### Seek `-ss`
seek/start to offset using `<time>`

```
-ss 01:02:03
-ss 10
```

### Duration `-t`
- `-t` duration of clip (overrides -to)

### End `-to`
- `-to`  end time of clip

### Time `<time>`
- `<time>` is specified as `HH:MM:SS.MILLISECONDS`
