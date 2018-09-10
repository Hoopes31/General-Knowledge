# Docker Compose 🐋

How to run multiple containers from a single file

This overview is based on a _[video](https://www.youtube.com/watch?v=HUpIoF_conA
)_ by Raghav Pal

## What is Docker Compose?

- A tool for defining and running multi-container applications
- Docker Compose is a scaleable solution

## Install

- [Installation Instructions](https://docs.docker.com/compose/install/)
- If you have python and pip you can also just run `pip install -U docker-compose`

## Creating a Docker Compose file

1. Create a file named _docker-compose.yml_
2. Define your required **Services**
    ``` Docker-Compose
    version: {DOCKER-COMPOSE-VERSION-NUMBER}
    services:
      {NAME-OF-YOUR-SERVICE}:
        image: {IMAGE-OF-YOUR-SERVICE}

      {NAME-OF-YOUR-SERVICE}:
        image: {IMAGE-OF-YOUR-SERVICE}
    ```
3. Run `docker-compose config`
4. Run `docker-compose up`
5. Run `docker-compose down`

_Run all these commands in the same directory_

## Commands

- `docker-compose --help` prints help menu
- `docker-compose -v` prints version name
- `docker-compose config` checks the validity of your docker-compose file
      - If you run into an error here run docker -v to check the version number of you docker setup. Check this version number against this [site](https://docs.docker.com/compose/compose-file/) to get the compose version.
- `docker-compose up` starts the _docker-compose.yml_ file in the current directory
      - `-d` runs the compose file in the background, allowing you to use your current terminal for further commands
      - `--scale {SERVICE-NAME=NUMBER-OF-SERVICES}` scales specified service to provided number
- `docker-compose down` stops Docker Compose

## Examples

1. Simple _docker-compose.yml_ that names a few images to be executed
    ```Docker-Compose
    version: 3
    services:
      web:
        image: nginx

      database:
        image: redis
    ```

2. More advanced commands for services can be found on the docker hub. Advanced commands include exposing ports and other container specific commands.
    ```Docker-Compose
    version: 3
    services:
      web:
        image: nginx
        ports:
        - 8080:80/tcp

      database:
        image: redis
    ```
