## Install Docker engine
...

## Useful commands
```
stop all container - docker kill $(docker ps -q)
remove all stoped containers - docker rm $(docker ps -a -q)
remove all images - docker rmi $(docker images -q)
```

## Use docker without sudo
```
sudo groupadd docker
sudo gpasswd -a $USER docker
newgrp docker
```
- ~~(sudo usermod -aG docker $USER)~~

## Run / Check
```
- docker ps
- docker ps -a
- docker images
- docker search jenkins
- docker pull jenkins
- docker run -it -p 8087:8080 jenkins
- docker run -d -p 8087:80 jenkins
- docker run selenium:latest - latest
```

## Different cases
```
docker rename [current-name] [new-name]
docker container top - process list in one container
docker container inspect - details of one container config
docker container stats - preformance stats for all containers

docker container run -it - start new container interactively 
docker container exec -it - run additional command in existing container


docker exec [container name] env  - get list of env for current container

```

## Stop / Remove

- ```docker stop containerId```
- ```docker rm containerId```
- ```docker rmi imageId```

## Volume
```
docker volume create VOLUME_NAME    - (creates volume in /var/lib/docker/volumes)
docker volume rm VOLUME_NAME        - actually you can remove several volumes
docker volume inspect VOLUME_NAME   - detailed info about volume(s)
docker volume ls - list of volumes


docker run -v VOLUME_NAME:/containerdir IMAGE_NAME - using of created volume
docker volume prune - it will remove from the system any volume not attached to a running or stopped container

> Example 1:
docker run -v /hostdir:/containerdir IMAGE_NAME - just linking
> Example 2:
docker volume create logdata
docker run -it --name volume1 --mount type=volume,source=logdata,target=c:\logdata microsoft/windowsservercore powershell
```
## Most common commands
* **docker stop $(docker ps -q)docker rm $(docker ps -a -q)** - stop and remove all the running containers

## Build / Exec
```
 docker build -t akram .
 docker tag akram-sprint akram-staging:v1
 docker exec -it 7845r41eh99 /bin/bash
 docker commit 7845r41eh99 repository:latest
 docker tag d583c3ac45fd repository/app:latest
 docker push repository/app:tag
```

## Docker some kind of information about container
```
docker stats containerName - cpu, ram , pid, net i/o , block i/o
docker logs containerName 
```

## Linking
```
# run redis container
    docker run --name some-redis -d redis

    #run rabbitmq container
    docker run -d --hostname my-rabbit --name some-rabbit rabbitmq

    #run webapps container
    docker run --name webapps -p 8080:80 --link some-redis:redis --link some-rabbit:rabbitmq nimmis/apache-php7
```

## Network
```
docker network ls
docker network inspect 
docker network create --driver my-bridge-network
or
docker network create -d bridge my-bridge-network

docker network connect [network-name] [container-name]
docker network disconnect [network-name] [container-name]
docker network rm [network-name]
```

## Dockerfile
INSTRUCTION | DESCRIPTION
--- | ---
FROM | This must be the first instruction in the Dockerfile and identifies the image to inherit from.
MAINTAINER|Provides visibility and credit to the author of the image
RUN|Executes a Linux command for configuring and installing
ENTRYPOINT|The final script or application used  to bootstrap the container, making it an executable application
CMD|Provide default arguments to the ENTRYPOINT using a JSON array format
LABEL|Name/value metadata about the image
ENV|Sets environment variables
COPY|Copies files into the container
ADD|Alternative to copy
WORKDIR|Sets working directory for RUN, CMD, ENTRYPOINT, COPY, and/or ADD instructions
EXPOSE|Ports the container will listen on
VOLUME|Creates a mount point
USER|User to run RUN, CMD, and/or ENTRYPOINT instructions

## Common 
```
ENTRYPOINT указывает команду, которая всегда будет выполняться при запуске контейнера.
CMD указывает аргументы, которые будут переданы в ENTRYPOINT
```

## Docker Hub
- ```docker login```
- ```docker logout```
- ```docker push repository/image:tag```

Useful links
* [Getting started with Docker [ENG]](https://dzone.com/refcardz/getting-started-with-docker-1?chapter=1)
* [Habr - Dockerfile [RU]](https://habr.com/ru/company/infobox/blog/240623/)
