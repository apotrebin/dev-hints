## Install Docker engine
...

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

## Stop / Remove

- ```docker stop containerId```
- ```docker rm containerId```
- ```docker rmi imageId```

## Build / Exec
```
 docker build -t akram .
 docker tag akram-sprint akram-staging:v1
 docker exec -it 7845r41eh99 /bin/bash
 docker commit 7845r41eh99 repository:latest
 docker tag d583c3ac45fd repository/app:latest
 docker push repository/app:tag
```

## Linking 
```
#run redis container
    docker run --name some-redis -d redis

    #run rabbitmq container
    docker run -d --hostname my-rabbit --name some-rabbit rabbitmq

    #run webapps container
    docker run --name webapps -p 8080:80 --link some-redis:redis --link some-rabbit:rabbitmq nimmis/apache-php7
```

## Network
```
docker network ls
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

## Docker Hub
- ```docker login```
- ```docker logout```
- ```docker push repository/image:tag```

Useful links
* [Getting started with Docker [ENG]](https://dzone.com/refcardz/getting-started-with-docker-1?chapter=1)
* [Habr - Dockerfile [RU]](https://habr.com/ru/company/infobox/blog/240623/)
