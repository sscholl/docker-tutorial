# Docker for Windows
https://docs.docker.com/docker-for-windows/

## Version Check
```
docker --version
docker-compose --version
docker-machine --version
```

## Basic Commands
```
docker info
docker images
docker ps -a
docker stop|rm|rmi <container>
```

## Running a Container
```
docker run --rm hello-world
docker run --rm -it ubuntu bash
docker run -d -p 80:80 --name webserver nginx
```

## Advanced Commands
```
docker inspect <container>
docker exec <container> /bin/bash

# list volumes
docker volume ls

# show all images without tag or name
docker images --filter "dangling=true"

# Delete all stopped containers
docker rm $(docker ps -a -q)
# Delete all dangeling images
docker rmi $(docker images --filter "dangling=true" -q)
```
