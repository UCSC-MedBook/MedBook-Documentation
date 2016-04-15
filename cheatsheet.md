# Cheat Sheet

## General

##### Run app in production mode
`docker-compose up`

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

## Mongo

##### Interactive shell 
`docker run --net=medbook_default -it mongo:2.6.11 mongo --host mongo`

##### Restore exported collections (requires export files and load_from_exports.sh present in /tmp/su2c-dev)
`docker run -v /tmp/su2c-dev/:/su2c-dev  --net=medbook_default -it mongo:2.6.11 /su2c-dev/load_from_exports.sh`

## Misc

##### SSH Tunnel (localhost:7000 forwarded to remoteHost:8000)

`ssh -L 7000:remoteHost:8000 username@remoteHost`
