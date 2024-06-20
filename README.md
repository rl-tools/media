Good GIF settings:

```
ffmpeg -i input.mp4 -vf "setpts=PTS/1.5,fps=20,scale=720:-1:flags=lanczos,palettegen=max_colors=16" palette.png
```
```
ffmpeg -i input.mp4 -i palette.png -filter_complex "setpts=PTS/1.5,fps=50,scale=720:-1:flags=lanczos[x];[x][1:v]paletteuse" -gifflags -offsetting output.gif
```
