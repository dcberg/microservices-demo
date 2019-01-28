This directory provides scripts for building and pushing Docker images, and tagging new
releases. 

### env variables 

- `TAG` - git release tag. also serves as the Docker tag. 
- `REPO_PREFIX` - Docker repo prefix to push images. Format: `$user/$project`.  Resulting images will be of the
   format `$user/$project/$svcname:$tag`. 

### scripts 

1. `./make-docker-images.sh`: builds and pushes images to the specified Docker repository.
2. `./make-release-artifacts.sh`: injects updated images/tag into 
   `./release/kubernetes-manifests/demo.yaml`. 
3. `./restore-release-artifacts.sh`: restores image names/tags in `demo.yaml` to defaults
   (`adservice`, `cartservice`, etc.) 
4. `./make-release.sh`: runs scripts 1 and 2, then runs `git tag` / pushes updated manifests to master.
