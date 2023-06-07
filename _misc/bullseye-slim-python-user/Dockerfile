# syntax=docker/dockerfile:1

FROM arcanemachine/bullseye-slim

# install python
RUN apt-get update \
    && apt-get install -y python3

ARG user=${DOCKER_CONTAINER_USER:-user}
ARG user_home=/home/$user

# create a non-root user
RUN useradd --create-home --shell /bin/bash --no-log-init $user

# work as non-root user; start in user's home directory
USER $user
WORKDIR $user_home
