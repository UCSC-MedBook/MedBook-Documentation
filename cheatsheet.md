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
`docker run -v /home/ubuntu/dumps/:/hi --net=medbook_default -it mongo:2.6.11 mongorestore --host mongo /hi`

## Misc

##### SSH Tunnel (localhost:7000 forwarded to remoteHost:27017)

`ssh -L 7000:127.0.0.1:27017 username@remoteHost`

##### Mount remote on local filesystem

[Instructions from here](https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh)

[Install FUSE and SSHFS from the osxfuse site.](http://osxfuse.github.io/)

`sshfs -o allow_other,defer_permissions host@remote:/path/on/remote /path/on/local`

## tmux

| Command                      | Description |
| -----------------------------|-------------|
| `tmux`                       | Start new |
| `tmux new -s [name]`         | Start new session with name |
| `tmux a [-t name]`           | Attach to a session |
| `tmux ls`                    | List sessions |
| `C-b d`                      | Detach from session |
| `C-b %`                      | Split pane vertically |
| `C-b "`                      | Split pane horizontally |
| `C-b x`                      | Kill pane |
| `C-b [`                      | Freeze pane, start scrolling |

[More shortcuts](https://gist.github.com/MohamedAlaa/2961058)
