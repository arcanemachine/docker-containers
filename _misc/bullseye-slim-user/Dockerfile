# syntax=docker/dockerfile:1

# image
FROM arcanemachine/bullseye-slim

ARG user=${DOCKER_CONTAINER_USER:-user}
ARG user_home=/home/$user

# create a non-root user
RUN useradd --create-home --shell /bin/bash --no-log-init $user

# use non-root user
USER $user
WORKDIR /home/$user
