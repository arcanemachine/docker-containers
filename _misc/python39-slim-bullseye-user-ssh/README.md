# python39-slim-bullseye-ssh

Extends `arcanemachine/python39-slim-bullseye`. Has non-root user and SSH key.


### Features

- Added non-root user
  - Has `sudo` privileges (username is `user`).
  - Has SSH access.
- Runs as `user` by default
- Starts in home directory of `user`: `/home/user/` 
