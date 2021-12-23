# docker-apt-mirror
Docker image based on debian with apt-mirror and Nginx web server  

Forked from https://github.com/flomine/docker-apt-mirror and adapted for debian bullseye repo and docker-compose usage

## Quick Start

**NOTE**: The Docker command provided in this quick start is given as an example
and parameters should be adjusted to your need.

Launch the apt-mirror docker container as detailed below

## Usage

1. Adapt the mirror.list content in regards with your need (currently customised with debian bullseye repo)

2. Build the docker
```
    $ cd ./src
    $ docker build . -t apt-mirror
```

3. Adapt docker-compose content (host mount point for apt volume and network name)

4. Run with docker compose
```
    $ cd ..
    $ docker-compose up -d
```
5. Browse to `http://your-host-ip:80/debian` to access the repo.

NB: wait for full repository synchronisation before connecting your remote machines to the repo
