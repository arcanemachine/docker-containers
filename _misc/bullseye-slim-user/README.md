# bullseye-slim-user

Extends [arcanemachine:bullseye-slim](https://hub.docker.com/repository/docker/arcanemachine/bullseye-slim).


### Features

- Adds non-root user with `sudo` privileges
- Starts as `user` in `/home/user/`
- Username can be overridden by setting `DOCKER_CONTAINER_USERNAME` before building the image
