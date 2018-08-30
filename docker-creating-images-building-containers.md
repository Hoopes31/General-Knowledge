# Docker creating images & building containers 🐋
How to build a Dockerfile, converting the Dockerfile to an image, running the container

This overview is based on a _[video](https://www.youtube.com/watch?v=LQjaJINkQXY)_ by Raghav Pal

## Building Docker files

1. Create a file named _Dockerfile.txt_ with the following contents
    - **FROM {IMAGE/SCRATCH}** declares from where the image begins. Scratch gives you a blank image, which is a starting point for new images.
    - **MAINTAINER {YOUR-NAME} {<YOUR-EMAIL>}** contact information
    - **RUN {COMMANDS}** get executed during the building of an image
    - **CMD ["{COMMAND},", "{COMMAND}"]** gets executed when the container is created
2. Run `docker build -t {IMAGE-NAME:TAG} {PATH-TO-Dockerfile}` to build the Dockerfile into an image
3. Run `docker run {IMAGE-ID}` to run the newly created docker image

_There are many more commands that go into building a robust Dockerfile checkout the cheat sheet below to get started_

### Example file
```
# basic Dockerfile
FROM ubuntu

MAINTAINER anthony 

RUN apt-get update

CMD ["echo", "Hello Docker!"]
```

## Guide sites
[Dockerfile cheat sheet](https://github.com/wsargent/docker-cheat-sheet#dockerfile)