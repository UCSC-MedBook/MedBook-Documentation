# MedBook-Documentation

## DevOps

### Committing to the parent repo

The following steps should be taken when fixing a bug, committing, and pushing to production.

1. `git clone https://github.com/UCSC-MedBook/MedBook`
- `cd MedBook && ./init.sh`
- Make the necessary changes in the app submodules
- For each app submodule:
  1. Merge to the `develop` branch, push
  - Make sure the build passes on CircleCI
  - Decide on a release tag: `tag=v0.9.4`
  - `git checkout master && git merge --no-ff develop`
    - the merge commit message should be: "$tag: [summary of changes]"
  - `git tag -a TAG -m TAG`
  - `git push origin master --tags`
- Edit `docker-compose.yml` with the new tags for each app
- `git add -A`, commit, and push

### Deploying to production

1. Connect to the production server.
- Connect to the prod tmux session: `tmux a -t prod`
- Locate the parent MedBook repository: `cd ~/MedBook`
- Update all code:
  - `git fetch`
  - `git status` to confirm everything looks reasonable
  - `git pull` to actually update
  - `init.sh` to update the submodules.
- Run `./scripts/prepare_for_deploy.sh`. This will pull all non-cached images from Docker Hub
- Press Ctrl-C to stop the site.  Once all containers are spun down, `docker-compose up` to start it again. This system will cause a short downtime.
