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


## Docker Tag


To tag the latest stabele build you can use `docker tag <repo/image> <repo/image:version>`:

```
docker tag smart48/smt-nginx smart48/smt-nginx:1.0
```

You will on listing then see the newly added version:

```
docker images |grep nginx
smart48/smt-nginx              1.0                 b2848533c584        33 seconds ago      30.3MB
smart48/smt-nginx              latest              b2848533c584        33 seconds ago      30.3MB
smt-docker_nginx               latest              a25e3d99664e        4 months ago        25.8MB
nginx                          alpine              ecd67fe340f9        5 months ago        21.6MB
```

## Docker Push

And then to push the built image you run:

```
docker image push smart48/smt-nginx
```

and have the latest pushed as tag.

Or if you did tag the image - and for production it is better to work with versioned images - you run the following:

```
docker image push smart48/smt-nginx:1.0
```