# docker-alpine-ftp-server
[![Docker Stars](https://img.shields.io/docker/stars/zerosuxx/alpine-ftp-server.svg)](https://hub.docker.com/r/zerosuxx/alpine-ftp-server/) [![Docker Pulls](https://img.shields.io/docker/pulls/zerosuxx/alpine-ftp-server.svg)](https://hub.docker.com/r/zerosuxx/alpine-ftp-server/) [![Docker Automated build](https://img.shields.io/docker/automated/zerosuxx/alpine-ftp-server.svg)](https://hub.docker.com/r/zerosuxx/alpine-ftp-server/) [![Docker Build Status](https://img.shields.io/docker/build/zerosuxx/alpine-ftp-server.svg)](https://hub.docker.com/r/zerosuxx/alpine-ftp-server/) [![MicroBadger Layers](https://img.shields.io/microbadger/layers/zerosuxx/alpine-ftp-server.svg)](https://hub.docker.com/r/zerosuxx/alpine-ftp-server/) [![MicroBadger Size](https://img.shields.io/microbadger/image-size/zerosuxx/alpine-ftp-server.svg)](https://hub.docker.com/r/zerosuxx/alpine-ftp-server/)

Small and flexible docker image with vsftpd server

## Usage
```
docker run -d \
            -p 21:21 \
            -p 21000-21010:21000-21010 \
            -e USERS="one|1234" \
            zerosuxx/alpine-ftp-server
```

## Configuration

Environment variables:
- `USERS` - space and `|` separated list (optional, default: `ftp|alpineftp`)
  - format `name1|password1|[folder1][|uid1] name2|password2|[folder2][|uid2]`
- `ADDRESS` - external address witch clients can connect passive ports (optional)
- `MIN_PORT` - minamal port number may be used for passive connections (optional, default `21000`)
- `MAX_PORT` - maximal port number may be used for passive connections (optional, default `21010`)

## USERS examples

- `user|password foo|bar|/home/foo`
- `user|password|/home/user/dir|10000`
- `user|password||10000`
