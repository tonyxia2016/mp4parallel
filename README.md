# mp4parallel
A script convert h264/aac media on cluster.

## Usages
Edit script file, replace "one.sample.com" with your own server or add some others.
```
parallel --env _ff_encode  \
    -S 1/root@one.sample.com \
    -S 1/root@two.sample.com \
    --trc {.}.target.mkv _ff_encode {} {.}.target.mkv
```
Run with:
```
mp4parallel <input_files...>
```
Accepted environmental variables:
- ACOPY   (Copy audio)
- ANONE   (Drop audio)

## Depend
- mkvtoolnix
- ffmpeg(with x264 build-in)
- parallel
- neroaacenc
