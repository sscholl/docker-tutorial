Content of Dockerfile
- FROM: the base image
- MAINTAINER: maintainer metadata
- CMD: command to be executed on startup (can be overridden)
- RUN: execute command on build time
- ENV: set environment variable
- EXPOSE: open port
- ADD: add files to image from local file system or url

Build image and start container
```
# create image
docker build -t="myapache" .

# run in background and check site
docker run --name apache -d -p 80:80 myapache
curl localhost

docker rm apache -f

# change content of index.html
docker build -t="myapache" .
docker run --name apache -d -p 80:80 myapache
curl localhost

docker exec -it apache top
```



Cleanup
```
# Delete all containers
docker rm $(docker ps -a -q) -f
# Delete all dangeling images
docker rmi $(docker images --filter "dangling=true" -q) myapache
```
