# hello-c

A simple hello world with Docker

## Building hello-c

With all the files in the same folder, build the container and add the tag hello-c:latest to it. Make sure to copy the dot after latest.

```
docker build --tag hello-c:latest .
```

You can list all Docker Images installed in your machine with:

```
docker image ls
```

## Running with Docker run

Launching the Container Image:

```
docker run -it --rm hello-c:latest
hello, world!
```

## Running with docker compose

*docker-compose.yml*
```
services:
  hello-c:
    image: hello-c:latest
```

Running Docker Compose App:

```
docker compose up
[+] Running 1/1
 ⠿ Container hello-c-hello-c-1  Created                                                                                                                                0.3s
Attaching to hello-c-hello-c-1
hello-c-hello-c-1  | hello, world!
hello-c-hello-c-1  | hello, world!
```