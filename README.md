# docker-apt-mirror
Docker image based on debian with apt-mirror and Nginx web server  

Forked from https://github.com/flomine/docker-apt-mirror and adapted for debian bullseye repo and docker-compose usage

NB: debian bug 932112 (Translation files not gathered) corrected by modifying apt-mirror scrip as per https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=932112

## Quick Start

**NOTE**: The Docker command provided in this quick start is given as an example
and parameters should be adjusted to your need.

Launch the apt-mirror docker container as detailed below

## Usage

1. Adapt the mirror.list content in regards with your need (currently customised with debian bullseye repo without including source files)

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

6. Modify the /etc/apt/sources.list file of your client machines for pointing to your new local repository, mentioning the arch used (amd64 in the current example). Example is here provided for convenience:
```
    deb [arch=amd64] http://services/debian/ bullseye main non-free contrib
    deb-src http://deb.debian.org/debian/ bullseye main non-free contrib

    deb [arch=amd64] http://services/debian-security bullseye-security main contrib non-free
    deb-src http://security.debian.org/debian-security bullseye-security main contrib non-free
```