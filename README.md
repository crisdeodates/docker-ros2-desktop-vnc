# docker-ros2-desktop-vnc

[![Publish to Registry](https://github.com/Tiryoh/docker-ros2-desktop-vnc/workflows/Publish%20to%20Registry/badge.svg?branch=master)](https://github.com/Tiryoh/docker-ros2-desktop-vnc/actions?query=workflow%3A%22Publish+to+Registry%22+branch%3Amaster)
[![Docker Automated build](https://img.shields.io/docker/automated/tiryoh/ros2-desktop-vnc)](https://hub.docker.com/r/tiryoh/ros2-desktop-vnc)
[![](https://img.shields.io/docker/pulls/tiryoh/ros2-desktop-vnc.svg)](https://hub.docker.com/r/tiryoh/ros2-desktop-vnc)

[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.0-4baaaa.svg)](code_of_conduct.md)

Dockerfiles to provide HTML5 VNC interface to access Ubuntu LXDE + ROS2, based on [dorowu/ubuntu-desktop-lxde-vnc](https://github.com/fcwu/docker-ubuntu-vnc-desktop)

ROS 1 version: https://github.com/Tiryoh/docker-ros-desktop-vnc

![Image from Gyazo](https://i.gyazo.com/5a71a36dc9d6106ef794fbcb86af7e7f.gif)

There are official ROS 2 Docker images provided by Open Robotics.  
https://github.com/osrf/docker_images/blob/master/README.md#official-library

このツールの詳細については以下の記事で紹介しています。  
The details of these tools are written in Japanese on this page.  
https://memoteki.net/archives/2955

## Quick Start

Run the docker container and access with port `6080`.  
Change the `shm-size` value depending on the situation.

```
docker run -p 6080:80 --shm-size=512m tiryoh/ros2-desktop-vnc:foxy
```

__NOTE__: `--security-opt seccomp=unconfined` flag is required to launch humble image. See https://github.com/Tiryoh/docker-ros2-desktop-vnc/pull/56.

```
docker run -p 6080:80 --shm-size=512m --security-opt seccomp=unconfined tiryoh/ros2-desktop-vnc:humble
```

Browse http://127.0.0.1:6080/.

![Image from Gyazo](https://i.gyazo.com/ab43ab3f6dc10b5186416499e49d0bbe.jpg)

## Build

To build Docker image from this Dockerfile, run the following command.

* dashing
```
cd dashing && docker build -t tiryoh/ros2-desktop-vnc:dashing .
```

* eloquent
```
cd eloquent && docker build -t tiryoh/ros2-desktop-vnc:eloquent .
```

* foxy
```
cd foxy && docker build -t tiryoh/ros2-desktop-vnc:foxy .
```

* galactic
```
cd galactic && docker build -t tiryoh/ros2-desktop-vnc:galactic .
```

* humble
```
cd humble && docker build -t tiryoh/ros2-desktop-vnc:humble .
```

* rolling
```
cd rolling && docker build -t tiryoh/ros2-desktop-vnc:rolling .
```

## Docker tags on hub.docker.com

* ~~[`dashing`](https://hub.docker.com/r/tiryoh/ros2-desktop-vnc/tags?page=1&name=dashing) which is based on [`dashing/Dockerfile`](./dashing/Dockerfile)~~ deprecated
* ~~[`eloquent`](https://hub.docker.com/r/tiryoh/ros2-desktop-vnc/tags?page=1&name=eloquent) which is based on [`eloquent/Dockerfile`](./eloquent/Dockerfile)~~ deprecated
* [`foxy`](https://hub.docker.com/r/tiryoh/ros2-desktop-vnc/tags?page=1&name=foxy) which is based on [`foxy/Dockerfile`](./foxy/Dockerfile)
* ~~[`galactic`](https://hub.docker.com/r/tiryoh/ros2-desktop-vnc/tags?page=1&name=galactic) which is based on [`galactic/Dockerfile`](./galactic/Dockerfile)~~ deprecated
* [`humble`](https://hub.docker.com/r/tiryoh/ros2-desktop-vnc/tags?page=1&name=humble), [`latest`](https://hub.docker.com/r/tiryoh/ros2-desktop-vnc/tags?page=1&name=latest) which is based on [`humble/Dockerfile`](./humble/Dockerfile)
* [`rolling`](https://hub.docker.com/r/tiryoh/ros2-desktop-vnc/tags?page=1&name=rolling) which is based on [`rolling/Dockerfile`](./rolling/Dockerfile)

Docker tags and build logs are listed on this page.  
https://github.com/Tiryoh/docker-ros2-desktop-vnc/wiki

## Related projects

* https://github.com/atinfinity/nvidia-egl-desktop-ros2
  * Dockerfile to use ROS 2 on Xfce Desktop container with NVIDIA GPU support via VNC/[Selkies](https://github.com/selkies-project/selkies-gstreamer)(Full desktop streaming with WebRTC)
* https://github.com/fcwu/docker-ubuntu-vnc-desktop
  * Dockerfile to access Ubuntu Xfce/LXDE/LxQT desktop environment via web VNC interface 

## License

Copyright 2020 Tiryoh\<tiryoh@gmail.com\>

This repository is released under the Apache License 2.0, see [LICENSE](./LICENSE).  
Unless attributed otherwise, everything in this repository is under the Apache License 2.0.

### Acknowledgements

This Dockerfile is based on [dorowu/ubuntu-desktop-lxde-vnc](https://github.com/fcwu/docker-ubuntu-vnc-desktop), licensed under the [Apache License 2.0](https://github.com/fcwu/docker-ubuntu-vnc-desktop/blob/60f9ae18e71e9fabbfb23f67b212e64ab72c206e/LICENSE).
