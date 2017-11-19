# Dockerized GoldenCheetah (WIP)

This is a basic working example at this stage.

It mostly follows the steps outlined in the offical GC [docs](https://github.com/GoldenCheetah/GoldenCheetah/blob/master/INSTALL-LINUX).

The Qt build steps are forked from [@rabits](https://github.com/rabits/dockerfiles/tree/master/6.9-desktop).

## Usage

```
docker run -d --rm \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -v /dev/snd:/dev/snd \
    -e DISPLAY=unix$DISPLAY \
    -e QT_AUTO_SCREEN_SCALE_FACTOR=1 \
    -e XDG_RUNTIME_DIR=/tmp \
    --name goldencheetah \
    jmackie/goldencheetah
```

## Exposed Volumes

`/data/.goldencheetah`
Application data

`/files`
Mount point for files to be uploaded.

## Notes

You'll probably need to give docker the rights to access the X-Server with:

```
$ xhost +local:docker
```

## TODO

 - Reduce the size of the final image
 - Enable more features

## Links

https://github.com/rabits/dockerfiles
https://github.com/benlau/qtci/blob/master/bin/extract-qt-installer

