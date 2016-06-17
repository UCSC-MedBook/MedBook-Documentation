# Deployment

## Deploying on production

Connect to the production server.
Locate the parent MedBook repository: `cd ~/MedBook`

1. Run `./prepare_for_deploy.sh` in the parent repo. This will pull the latest commit, detect changed docker images and spin them up

2. Connect to the prod tmux session: `tmux a -t prod`

3. Press Ctrl-C to stop the site.  Once all containers are spun down, `docker-compose up` to start it again. Yes, this causes a short downtime.
