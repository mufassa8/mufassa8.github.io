---
title: run server with docker
author: Jaeman Lee
date: 2021-10-01 14:10:00 +0800
categories: [Docker Usage]
tags: [run-server]
render_with_liquid: false
---

## Basic running docker

```bash
$ docker run ${run-option} -n ${container-name-asYouWant} -p ${port}:${port} ${docker-image-name}
```

## Examples
- Jenkins
  - docker pull
    ```bash
        docker pull jenkins/jenkins:lts
    ## 'docker pull jenkins' is deprecated
    ```

  - docker run jenkins image as a container
    ```bash
    docker run -d --name ${CONTAINER_NAME_AS_YOU_WANT} -p ${MY_SERVER_PORT}:${CONTAINER_PORT} jenkins/jenkins:lts
    ```
    > **-d** : this option makes server be loaded on background
    

  - Enter running container with sudo author
    ```bash
    docker run -itu 0 ${CONTAINER_NAME} /bin/bash
    ```
    > **-itu**: this is compose of three options
    > - ***-i***(--interactive): Keep STDIN open even if not attached
    > - ***-t***(--tty): Allocate a pseudo-TTY(tty: linux console or termianl)
    > - ***-u***(--user): Username or UID (format: `<name|uid>[:<group|gid>])`
    
  - edit port where jenkins will be loaded (port is assigned on 8080 default, but 8080 is so popular that it may occur conflicts later)

## Change Path

kakao repo works fine in Korea.

These are example for `/etc/apt/sources.list`.

Try to change into this.

```
# See sources.list(6) manpage for more information# Remember that CD-ROMs, DVDs and such are managed through the apt-cdrom tool.
deb http://mirror.kakao.com/ubuntu focal universe

deb http://mirror.kakao.com/ubuntu focal-updates universe

deb http://mirror.kakao.com/ubuntu focal multiverse

deb http://mirror.kakao.com/ubuntu focal-updates multiverse

deb http://mirror.kakao.com/ubuntu focal-backports main restricted universe multiverse

deb http://mirror.kakao.com/ubuntu focal-security main restricted

deb http://mirror.kakao.com/ubuntu focal-security universe

deb http://mirror.kakao.com/ubuntu focal-securtiy multiverse
```

and check apt works well.
```bash
$ sudo apt-get update
```
