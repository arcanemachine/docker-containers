# syntax=docker/dockerfile:1

FROM docker.io/python:3.9-slim-bullseye

# create unprivileged user
ARG USERNAME=user
RUN useradd --create-home --shell /bin/bash --no-log-init $USERNAME

# work as unprivileged user
USER $USERNAME
WORKDIR /home/user
