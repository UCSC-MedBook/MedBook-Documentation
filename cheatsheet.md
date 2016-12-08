# Cheat Sheet
  - [General](#general)
  - [Docker](#docker)
  - [Mongo](#mongo)
  - [Misc](#misc)
  - [tmux](#tmux)
  - [Git](#git)
  - [Mysql](#mysql)
  - [TravisCI](#travisci)

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

##### Follow logs of all the containers
`docker-compose logs --follow --tail 10`

##### Remove orphaned docker volumes (frees up significant space)
`docker volume ls -qf dangling=true | xargs -r docker volume rm`

##### Parse docker-compose files to confirm correct indentation etc.
Prints the resulting yaml if parseable; otherwise, throws error.

`docker-compose -f docker-compose.yml -f docker-compose-dev.yml config`

##### Start a single container in the docker-compose context
For example, if you've `docker stop`ped it. Doesn't start dependency containers (eg mongo)

`docker-compose -f docker-compose.yml -f docker-compose-dev.yml run --no-deps --service-ports `*`patient-care`*

##### Restart docker

`sudo /etc/init.d/docker restart`

## Mongo

##### Interactive shell
`docker run --net=medbook_default -it mongo:2.6.11 mongo --host mongo`

##### Interactive shell -- staging
`mongo MedBook -host mongo-staging`

##### Restore exported collections (requires export files and load_from_exports.sh present in /tmp/su2c-dev)
`docker run -v /home/ubuntu/dumps/:/hi --net=medbook_default -it mongo:2.6.11 mongorestore --host mongo /hi`

### Mongo shell commands
##### Pretty print
`db.CollectionName.find({criteria}).pretty()`
##### List collections or databases
`show collections`

`show dbs`

##### Sort by a field
`db.CollectionName.find().sort({fieldname: 1})` or -1 for reverse sort

## Misc

##### SSH Tunnel for MedBook dev boxes

`ssh -L 8000:127.0.0.1:8000 username@remoteHost`

(In general: *xxxx*:127.0.0.1:*yyyy* forwards localhost port *xxxx* to remoteHost port *yyyy* ).
###### SSH tunnel for single app when not using Gateway:
`docker inspect `*`foo`*` | grep IPAddress` and use that address instead of 127.0.0.1 above; port is typically 3000.


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

## Git
##### Populate all submodule directories
`git submodule update --init --recursive`
##### new feature branch
`git checkout -b f-gsea-new`
##### Network-style commit log
`git log --graph --oneline --all`

[GitFlow branching model documentation](https://datasift.github.io/gitflow/GitFlowForGitHub.html)

## mysql
import a sql dump into mysql database on local machine

`mysql -h hostname -u <user> -p<Password> cbioportal < dump.sql`  (note: there is no space before the password)

`docker run -v /mnt/mysql-dump/:/hi mysql:5.7 bash -c "mysql -u root -pasdfasdf cbioportal < /hi/dump.sql"`

## TravisCI
For documentation or ansible changes that shouldn't trigger a travis build:

If you don’t want to run a build for a particular commit any reason add `[ci skip]` or `[skip ci]` to the git commit message. [via](https://docs.travis-ci.com/user/customizing-the-build/#Skipping-a-build)

For pull requests, [skip ci] must be added to ALL commits in the pull request (as opposed to the pull request message itself) to prevent travis from running CI.
