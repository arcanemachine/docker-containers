# syntax=docker/dockerfile:1

# image
FROM arcanemachine/bullseye-slim-user

# use root account to install packages
USER root

# install gnupg for key verification
RUN apt-get update && \
    apt-get install -y gpg

# install ansible (https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-debian)
RUN echo "deb http://ppa.launchpad.net/ansible/ansible/ubuntu focal main" > /etc/apt/sources.list.d/ansible.list \
    && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 93C4A3FD7BB9C367 \
    && apt-get update \
    && apt-get install -y ansible

# install useful utilites
RUN apt-get update && \
    apt-get install -y vim

# use non-root account
USER user

# clone ansible scripts repo
