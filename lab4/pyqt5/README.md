# pyqt5

A simple hello world with python qt5 using Docker.

Because the example accesses Wayland socket must be executed with superuser (root).
Switch to root user and follow the next steps as root.

```
sudo su
(passworld) fio
```

## Building pyqt5

With all the files in the same folder, build the container and add the tag my-pyqt5:latest to it. Make sure to copy the dot after latest.

```
docker build -t my-pyqt5:latest .
```

You can list all Docker Images installed in your machine with:

```
docker image ls
```

## Running with Docker run

Launching the Container Image:

```
docker run -it -d -v /run/user/63:/run/user/63 -v /dev/dri:/dev/dri -v /dev/pvr_sync:/dev/pvr_sync --device-cgroup-rule='c 226:* rmw' --device-cgroup-rule='c 10:* rmw' --env QT_QPA_PLATFORM=wayland –env WAYLAND_DISPLAY="wayland-0" my-pyqt5:latest
```

## Running with docker compose

*docker-compose.yml*
```
version: '3.6'

services:
  pyqt5:
    image: pyqt5:latest
    restart: always
    network_mode: "host"
    volumes:
      - /run/user/63:/run/user/63
      - /dev/dri:/dev/dri
      - /dev/pvr_sync:/dev/pvr_sync
    device_cgroup_rules:
      - 'c 226:* rmw'
      - 'c 10:* rmw'  
    environment:
      QT_QPA_PLATFORM: "wayland"
      WAYLAND_DISPLAY: "wayland-0"
```

Running Docker Compose App:

```
docker compose up
[+] Running 1/1
 ⠿ Container pyqt5-pyqt5-1  Created                                                                                                                                0.3s
Attaching to pyqt5-pyqt5-1
```