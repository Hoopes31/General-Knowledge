# Docker volumes

Creating volumes, connecting volumes to containers

This overview is based on a _[video](https://www.youtube.com/watch?v=VOK06Q4QqvE)_ by Raghav Pal

## What is a volume

- Storage for a docker container that lives outside of the container itself
- This provides a means for keeping data when the container is shutdown

## Creating a volume

1. `docker volume create {VOLUME-SOURCE}` creates a docker volume named {VOLUME-SOURCE}
2. `docker run --name {YOUR-CHOICE-OF-CONTAINER-NAME} -v {VOLUME-SOURCE:CONTAINER-PATH} {IMAGE-NAME}` creates a container by the given name and connects the created volume to the named container.
- `VOLUME-NAME` can also be a path on your computer. This is useful if you want a copy of your data locally.

## Volume commands

- `docker volume --help` prints help menu for volumes
- `docker ls` prints volumes
- `docker volume inspect {VOLUME-NAME}` prints volume information
- `docker rm {VOLUME-NAME}` removes the volume
- `docker volume prune` removes the volumes not in use by a container
