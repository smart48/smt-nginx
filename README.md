# Smart48 Nginx

Smart48 Nginx Docker Image in progress.

The Laradock Nginx image had the `daemon off` was in nginx config and Dockerfile so removed in the config as suggested by [Kyle Mathew](https://github.com/KyleAMathews/docker-nginx/issues/5)


Also had

```
2020/06/02 06:26:21 [emerg] 1#1: host not found in upstream "php-fpm:9000" in /etc/nginx/conf.d/upstream.conf:1
nginx: [emerg] host not found in upstream "php-fpm:9000" in /etc/nginx/conf.d/upstream.conf:1
```

on running `docker run --name smt-nginx -p 81:80 -d smart48/smt-nginx:latest`

so this image was missing the PHP FPM container on a cold `run`.

## Docker Build

To build for our own Smart48 Docker Hub repository we use

```
docker build . -t smart48/smt-nginx
```

This will build with the tag using our organization's name and name for the image.

you can test it using 

```
docker run --name smt-nginx -p 81:80 -d smart48/smt-nginx:latest
```

**NB** `docker container stop $(docker container ls -aq)` to stop all running containers and `docker container rm $(docker container ls -aq)` to remove all.

## Docker Push

And then to push the built image you run:

```
docker image push smart48/smt-nginx
```
