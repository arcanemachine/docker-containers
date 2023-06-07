# docker-containers

A ready-made collection of Docker + Compose files to get up and running with minimal hassle

### WARNING: These container configurations are not intended for a use in a production environment! They are made to easily get up and running in a development environment.

Notes:

- I use the containers in this repo to get things up and running with minimal hassle.
- Some container environments may require you to configure environment variables.
  - You can do this by creating a `.env` file that contains the desired environment variables.
    - Some directories will contain an `example.env` file that can be used as a template for the `.env` file. Just copy `example.env` to `.env` and modify the file as needed.
  - NOTE: All `.env` files are gitignored and will not be committed to the repository.
- Some directories do not contain a base `compose.yaml` file (e.g. `php/`).
  - In these directories, you must specify which Compose file(s) you want to use via the `-f` flag:
    - e.g. `docker compose -f compose.mariadb.yaml up`
- The `_misc` directory has a bunch of miscellaneous experimental stuff from when I was learning how Docker works, so it's a bit of a hodgepodge.
