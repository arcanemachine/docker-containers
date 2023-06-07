# syntax=docker/dockerfile:1

FROM python:3.9-slim-bullseye

# fixme
RUN echo "*** THIS DOCKERFILE HASN'T BEEN CHECKED. ***"
RUN echo "*** CHECK IT OVER TO MAKE SURE IT MAKES SENSE BEFORE USING IT!!! ***"
RUN echo "*** THIS DOCKERFILE HASN'T BEEN CHECKED. ***"
RUN echo "*** CHECK IT OVER TO MAKE SURE IT MAKES SENSE BEFORE USING IT!!! ***"
RUN echo "*** THIS DOCKERFILE HASN'T BEEN CHECKED. ***"
RUN echo "*** CHECK IT OVER TO MAKE SURE IT MAKES SENSE BEFORE USING IT!!! ***"
RUN exit 1

# install ssh server
RUN apt-get update \
    && apt-get -y install openssh-server

# create a non-root user
RUN useradd --create-home --shell /bin/bash --no-log-init $user

# give user sudo privileges
RUN apt-get update\
    && apt-get install -y sudo\
    && echo $user ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$user \
    && chmod 0440 /etc/sudoers.d/$user

# create ssh config folder for user, with proper permissions
RUN mkdir $user_home/.ssh \
    && chown $user:$user $user_home/.ssh \
    && chmod 700 $user_home/.ssh

# copy public key to 'authorized_keys' file and set proper permissions
COPY id_rsa.pub ${user_home}/.ssh/authorized_keys
RUN sudo chown $user:$user $user_home/.ssh/authorized_keys \
    && chmod 600 $user_home/.ssh/authorized_keys

# work as non-root user; start in user's home directory
USER $user
WORKDIR $user_home

# expose port 22 for ssh
EXPOSE 22

# start the ssh server
RUN sudo mkdir /var/run/sshd
CMD ["sudo", "/usr/sbin/sshd", "-D"]
