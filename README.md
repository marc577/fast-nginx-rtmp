# fast-nginx-rtmp
A Dockerfile installing NGINX, nginx-rtmp-module from source. Built on Alpine Linux.

* Nginx 1.17.10 (Latest version compiled from source)
* nginx-rtmp-module 1.2.1 (compiled from source)

[![Docker Stars](https://img.shields.io/docker/stars/alfg/nginx-rtmp.svg)](https://hub.docker.com/r/marc577/fast-nginx-rtmp/)
[![Docker Pulls](https://img.shields.io/docker/pulls/alfg/nginx-rtmp.svg)](https://hub.docker.com/r/marc577/fast-nginx-rtmp/)
[![Docker Automated build](https://img.shields.io/docker/automated/alfg/nginx-rtmp.svg)](https://hub.docker.com/r/marc577/fast-nginx-rtmp/builds/)

## Usage

### Server
* Pull docker image and run:
```
docker pull marc577/fast-nginx-rtmp/
docker run -it -p 1935:1935 --rm marc577/fast-nginx-rtmp/
```
or 

* Build and run container from source:
```
docker build -t fast-nginx-rtmp .
docker run -it -p 1935:1935 --rm fast-nginx-rtmp
```

* Stream live content to:
```
rtmp://<server ip>:1935/live/$STREAM_NAME
```

### Environment Variables
This Docker image uses `envsubst` for environment variable substitution. You can define additional environment variables in `nginx.conf` as `${var}` and pass them in your `docker-compose` file or `docker` command.

### OBS Configuration
* Stream Type: `Custom Streaming Server`
* URL: `rtmp://localhost:1935/live`
* Stream Key: `yourName`

### Watch Stream
* In VLC use Networkstream:
```
rtmp://<server ip>/live/$STREAM_NAME
```

## Resources
* https://alpinelinux.org/
* http://nginx.org
* https://github.com/arut/nginx-rtmp-module
* https://obsproject.com
