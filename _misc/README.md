# docker-examples

This is a collection of Docker containers I've made to make life easier for myself and others.

Also included is a folder called `scripts` that perform many useful functions that I use frequently: starting/stopping/building containers, etc. This folder is symlinked into each project for portability and ease of use.

These examples were made in, and for, a Debian-based environment. While it may not make a difference outside that environment, some images (e.g. python39) are made to be used in Debian, so modifications may be needed to use them in, for example, CentOS.

## Environment

Each container folder contains a `.envrc` with parameters that can be modified to change the build.

This file can be modified and sourced manually with `source .envrc`. You can also use `[direnv](https://direnv.net/)` to load these parameters automatically whenever the terminal enters a folder containing a `.envrc` file.


## Usage

Navigate to `[container-name]/scripts-generic/`.

To build a container image:
  - `./build`

To create/run a new container:
  - `./run`

To enter the shell:
  - `./shell`

To stop a container:
  - `./stop`

To destroy a container:
  - `./destroy`


### Custom Container Names

To create a container with a custom name, use the `CONTAINER_NAME` environment variable. For example:
  - `CONTAINER_NAME=your-new-container ./run`
  - `CONTAINER_NAME=your-new-container ./shell`

## License

This repo is MIT licensed. Use it however you want to.
