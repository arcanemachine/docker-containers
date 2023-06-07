# container-postgres

A simple Postgres container for `podman` (or `docker`). Stores data in the `./volumes/` folder.

To use with Docker, you should be able to run the standard `docker-compose` commands `docker-compose up` and `docker-compose down`. You should also be able to comment out the `podman` section in the `start` and `stop` scripts and uncomment the `docker` parts if you want.

## Instructions

0. Ensure that `podman` and `podman-compose` are installed (or their Docker counterparts).
1. To start the container, run the `start` script.
1. To stop the container, run the `stop` script.
