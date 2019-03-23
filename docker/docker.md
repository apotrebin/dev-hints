## Install Docker engine
...

## Use docker without sudo
- ```sudo groupadd docker```
- ```sudo gpasswd -a $USER docker```
- ```newgrp docker```
- ~~(sudo usermod -aG docker $USER)~~

## Run / Check
- ```docker ps```
- ```docker ps -a```
- ```docker images```

- ```docker search jenkins```
- ```docker pull jenkins```
- ```docker run -it -p 8087:8080 jenkins``` - interact 
- ```docker run -d -p 8087:80 jenkins``` - as demon
- ```docker run selenium:latest``` - latest

## Stop / Remove

- ```docker stop containerId```
- ```docker rm containerId```
- ```docker rmi imageId```

## Build / Exec
- ```docker build -t akram .```
- ```docker tag akram-sprint akram-staging:v1```
- ```docker exec -it 7845r41eh99 /bin/bash```
- ```docker commit 7845r41eh99 akram-staging:latest```