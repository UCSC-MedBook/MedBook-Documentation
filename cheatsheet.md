# Cheat Sheet

## General

##### Run app in production mode
`docker-compose up`

##### Run some apps in development mode

`docker-compose -f docker-compose.yml -f docker-compose-dev.yml`

## Docker

##### List all running containers
`docker ps`

##### List all containers (including stopped ones)
`docker ps -a`

##### Stop container
`docker stop [CONTAINER_NAME]`

##### Stop all running containers
`docker ps -q | xargs docker stop`

##### Remove container (must be stopped)
`docker rm [CONTAINER_NAME]`

##### Bash session for running container
`docker exec -it [CONTAINER_NAME] /bin/bash`

##### Show docker images
`docker images`

##### Show image layers (w/ sizes)
`docker history [IMAGE_ID]`

##### Follow logs of single container
`docker logs --follow [CONTAINER_NAME]`

##### Remove orphaned docker volumes (frees up significant space)
`docker volume ls -qf dangling=true | xargs -r docker volume rm`

## Mongo

##### Interactive shell 
`docker run --net=medbook_default -it mongo:2.6.11 mongo --host mongo`

##### Restore exported collections (requires export files and load_from_exports.sh present in /tmp/su2c-dev)
`docker run -v /tmp/su2c-dev/:/su2c-dev  --net=medbook_default -it mongo:2.6.11 /su2c-dev/load_from_exports.sh`

## Misc

##### SSH Tunnel (localhost:7000 forwarded to remoteHost:27017)

`ssh -L 7000:127.0.0.1:27017 username@remoteHost`