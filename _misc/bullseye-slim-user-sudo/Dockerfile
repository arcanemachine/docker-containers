# syntax=docker/dockerfile:1

# image
FROM arcanemachine/bullseye-slim

ARG user=${DOCKER_CONTAINER_USER:-user}
ARG user_home=/home/$user

# create a non-root user
RUN useradd --create-home --shell /bin/bash --no-log-init $user

# give user sudo privileges
RUN apt-get update \
    && apt-get install -y sudo \
    && echo $user ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$user \
    && chmod 0440 /etc/sudoers.d/$user

# use non-root user
USER $user
WORKDIR /home/$user
