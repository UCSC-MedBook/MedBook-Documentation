# Deployment

## Deploying on production

Connect to the production server.
Locate the parent MedBook repository: `cd ~/MedBook`
1. Run `./prepare_for_deploy.sh` in the parent repo
  This will: Pull the latest commit, detect changed docker images and spin them up
Connect to the prod tmux session: `tmux a -t prod`
2. Press Ctrl-C to stop the site.  Once all containers are spun down, `docker-compose up` to start it again. Yes, this causes a short downtime.
