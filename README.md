# firefox X11

run new firefox browser on Alpine through X11 in docker

Image is based on the [alpine](https://hub.docker.com/_/alpine/) base image

## Docker image size


## Docker image usage

```
docker run [docker-options] user2k20/firefox
```

## Examples

Typical usage:

```
XSOCK=/tmp/.X11-unix
XAUTH=/tmp/.docker.xauth
xauth nlist :0 | sed -e 's/^..../ffff/' | xauth -f $XAUTH nmerge -
docker run --rm -e "DISPLAY=:1" -v $XSOCK:$XSOCK -v $XAUTH:$XAUTH -e XAUTHORITY=$XAUTH  user2k20/firefox
```

### Todo
- [ ] Provide more examples
