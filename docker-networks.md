# Docker networks

Creating networks, connecting networks to containers

## What is a docker network

- Communication network for connecting multiple containers within docker

## Creating a network

1. `docker network create --driver=bridge {NETWORK-NAME}` creates a docker network with provided network name

## Network commands

- `docker run {CONTAINER} --net={NETWORK-NAME}` connects a new container to the network
- `docker network connect {NETWORK-NAME} {CONTAINER}` connects existing network to a running docker container
- `docker network ls` lists existing networks