# syntax=docker/dockerfile:1

FROM arcanemachine/bullseye-slim

# install ssh server
RUN apt-get update \
    && apt-get -y install openssh-server

# create ssh config folder with proper permissions
WORKDIR /root
RUN mkdir .ssh && chmod 700 .ssh

# copy public key to 'authorized_keys' file and set proper permissions
COPY id_rsa.pub /root/.ssh/authorized_keys
RUN chmod 600 .ssh/authorized_keys

# expose port 22 for ssh
EXPOSE 22

# start the ssh server
RUN mkdir /var/run/sshd
CMD ["/usr/sbin/sshd", "-D"]
