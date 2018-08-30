# Docker getting started 🐋
Docker benefits, installation, general workflow, cli commands

This overview is based on a few videos by  _[Raghav Pal](https://www.youtube.com/watch?v=wi-MGFhrad0)_

## Why Docker?
Docker eases deployment by standardizing your environment with containers. This allows you to package your code and its dependencies into a shipable format. This gives you confidence in knowing your docker container that ran your test env is the same as your docker container that is running your production env. No more it works here, but not there.

## Installing Docker
1. [Download](https://www.docker.com/get-started)

## Docker terminology
- **Docker Container**: an application that runs within the docker environment
- **Docker Image**: templates used to create docker containers. Images hold all the dependency information needed to run the container.
- **Docker Engine**: The Docker engine is setup as a client server platform. Where the _client_ sends requests through the CLI or REST API calls to the _daemon (server)_. When the server receives a call from the client it interacts with its hosted containers and images.
- **Docker Hub**: A repository for docker images. Here you can store or download public docker images. 
- **Tags**: Version names, in Docker Hub, used to pull down docker images

## General workflow
1. Developer defines an applications dependencies/requirements in a single Dockerfile
2. The Dockerfile is then used to **create a docker image**
3. From the image you can **create a docker container**, aka the runtime instance of a docker image. The real deal version of your application.
4. Docker images can be stored in repos or the Docker Hub

## Basic CLI commands

### Docker commands
- `docker version` prints Docker Engine info; client and server
- `docker -v` prints docker version and build
- `docker info` prints containers, images, server version, driver info, plugins, swar info, runtimes, + more
- `docker --help` prints the help info for cli commands (running on its own gives all cli commands, but running with a cli command gives further details on that specific command)
- `docker login` allows you to login to Docker Hub

### Image commands
- `docker images` prints all docker images
- `docker pull {IMAGE-NAME}` pulls specified image
- `docker rmi {IMAGE-NAME}` removes specified image
- `docker commit {CONTAINER-ID} {NAME-OF-YOUR-CHOICE}` creates a copy of the selected container id and saves it with the name provided. This will save recently made changes.
- `docker run {IMAGE-NAME}` will run the provided image and create and start the associated container. _If the images does not exist in dockers local environment it will attempt to pull the image from the Docker Hub_
    - `-it` will run the **interactive shell** of the container you decide to run
    - `-name` allows you to name your image
    - `{IMAGE-NAME}:{TAG}` allows you to specify image version
    - `-p {LOCAL-PORT:DOCKER-PORT}` connects local port to the docker server port (can be flagged multiple times in one run call to connect many ports)
- `docker inspect {IMAGE-NAME}` print image information
- `docker history {IMAGE_NAME/ID}` prints image history

### Dockerfile commands
- `docker build -t {IMAGE_NAME:TAG} {PATH-TO-Dockerfile}` builds a Dockerfile into an image

### Container commands
- `docker start {CONTAINER-NAME/ID}` starts the named container
    - `i` attaches stdin to the interactive shell
- `docker stop {CONTAINER-NAME/ID}` stops the named container
- `docker ps` prints running containers
- `docker ps -a` prints all containers
- `docker pause {CONTAINER-NAME/ID}` keeps the container running but closes it to commands
- `docker unpause {CONTAINER-NAME/ID}` undoes pause
- `docker top {CONTAINER-NAME/ID}` prints PID USER TIME
- `docker stats {CONTAINER-NAME/ID}` prints MEMORY% IO CPU% MEMORY-USAGE
- `docker attach {CONTAINER-NAME/ID}` allows you to enter your containers command line
- 1. `exit` leaves the containers command line
- `docker kill {CONTAINER-NAME/ID}` kills a running container
- `docker rm {CONTAINER-NAME/ID}` removes a container

### System commands
- `docker stats` prings memory usage info, I/O
- `docker system df` prints dicks usage 
- `docker system prune` deletes and removes images and containers not currently running

## Example material
1. Start docker
2. Checkout your local images with `docker images` (should be none)
3. Run `docker run hello-world`. This will pull the docker image _hello-world_ from Docker Hub, create the container and run the sample application. 
4. Run `docker ps -a` and you should see the _hello-world_ application ran

