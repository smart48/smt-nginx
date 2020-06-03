# Smart48 Nginx

Information to be added ...

## Docker Build

To build for our own Smart48 Docker Hub repository we use

```
docker build . -t smart48/smt-nginx
```

This will build with the tag using our organization's name and name for the image.

## Test

You can test the build image using:

```
docker run --name smt-nginx -p 81:80 -d smart48/smt-nginx:latest
```

## Docker Push

And then to push the built image you run:

```
docker image push smart48/smt-nginx
```
