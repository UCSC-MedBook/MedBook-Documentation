# Deployment

## Deploying on production

1. `cd ~/MedBook` to go to the MedBook parent repo
2. `export LAST_HASH=$(git rev-parse HEAD)` to save the last hash of the parent repo
3. `git pull` in parent repo to load latest code
4. `./init.sh` for good measure
5. `git diff $LAST_HASH $(git rev-parse HEAD) docker-compose.yml | grep image | grep +` to see which images need to be pulled
6. `unset MONGO_URL` to make sure the apps don't actually start in the next step
7. `docker run medbook/CHANGED_APP:LATEST_TAG` for each of the changed images to pull them (they should fail!)
8. Now for the scary part: switch to the tmux pane where the logs are, `C-c` and then start it up again with `docker-compose up`
