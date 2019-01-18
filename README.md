# docker-apt-mirror
Docker image based on debian with apt-mirror and Nginx web server  

## Quick Start

**NOTE**: The Docker command provided in this quick start is given as an example
and parameters should be adjusted to your need.

Launch the apt-mirror docker container with the following command:
```
docker run -d \
    --name=apt-mirror \
    -p 80:80 \
    -v /volume1/docker/deb-repository:/var/spool/apt-mirror:rw \
    flomine/apt-mirror
```

Where:
  - `/volume1/docker/deb-repository`: This is where the application stores deb packages and all files needing persistency.

Browse to `http://your-host-ip:80` to access the repo.

## Usage

```
docker run [-d] \
    --name=apt-mirror \
    [-e <VARIABLE_NAME>=<VALUE>]... \
    [-v <HOST_DIR>:<CONTAINER_DIR>[:PERMISSIONS]]... \
    [-p <HOST_PORT>:<CONTAINER_PORT>]... \
    flomine/apt-mirror
```
| Parameter | Description |
|-----------|-------------|
| -d        | Run the container in background.  If not set, the container runs in foreground. |
| -e        | Pass an environment variable to the container.  |
| -v        | Set a volume mapping (allows to share a folder/file between the host and the container).  |
| -p        | Set a network port mapping (exposes an internal container port to the host). |
