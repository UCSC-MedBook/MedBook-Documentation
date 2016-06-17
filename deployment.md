# Deployment

## Deploying on production

`cd ~/MedBook` to go to the MedBook parent repo
`export LAST_HASH=$(git rev-parse HEAD)` to save the last hash of the parent repo
`git pull` in parent repo to load latest code
`./init.sh` for good measure
`git diff $LAST_HASH $(git rev-parse HEAD) docker-compose.yml | grep image | grep +` to see which images need to be pulled
`unset MONGO_URL` to make sure the apps don't actually start in the next step
`docker run medbook/CHANGED_APP:LATEST_TAG` for each of the changed images to pull them (they should fail!)
Now for the scary part: switch to the tmux pane where the logs are, `C-c` and then start it up again with `docker-compose up`
