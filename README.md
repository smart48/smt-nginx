# Smart48 Nginx

Smart48 Nginx Docker Image in progress.

## Docker Build

To build for our own Smart48 Docker Hub repository we use

```
docker build . -t smart48/smt-nginx
```

This will build with the tag using our organization's name and name for the image.
Docker Push

And then to push the built image you run:

```
docker image push smart48/smt-nginx
```
