Content of Dockerfile
- FROM: the base image
- MAINTAINER: maintainer metadata
- CMD: command to be executed on startup (can be overridden)

Build image and start container
```
# create image
docker build -t="mydockerfile" .

# run new container in foreground
docker run -it mydockerfile

# run container with bash
docker run -it mydockerfile /bin/bash
```

Cleanup
```
# Delete all containers
docker rm $(docker ps -a -q) -f
# Delete all dangeling images
docker rmi $(docker images --filter "dangling=true" -q) mydockerfile
```
