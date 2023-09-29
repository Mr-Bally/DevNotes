# Docker Compose

- - - -

## Table of Contents

* [What is Docker compose?](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerCompose.md#what-is-docker-compose)
* [Example](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerCompose.md#commands)
* [YAML](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerCompose.md#yaml)

## What is docker-compose?

* Often you typically have several applications running in conjunctions (especially when using microservices) e.g. a web application with a FE, cache and database
* `docker-compose` files allows you to define multiple service in a 'stack' and run them at the same time
* `docker-compose` files are written in a declarative style using YAML
* These are called "multi container" apps

## Commands

`docker-compose up -d` Uses a docker compose file to start multiple containers in detached mode
`docker-compose logs` View logs for all docker compose services
`docker-compose logs --trail=5` View the last 5 lines of the service logs
`docker-compose logs --follow` Follow log output in realtime
`docker-compose exec <serviceName> <shell>` This will allow you to shell into a container and move into the working directory of the container. The `shell` can be something like `sh`
`docker-compose up -d --scale <serviceName>=3` This will scale up the number of instances for a service to 3. Note: Do NOT define the host ports here as there will be multiple instances

## YAML

* YAML is a declarative configuration file which uses key-value pairs and lists (sequences) of items
* Indentation matters in YAML and you must use spaces instead of tabs

### Structure of YAML Files

`version : '3.1'` Defines the schema version for the YAML file (depending on the version this will change what is supported)
`services :` This defines the list of services you wish to run as part of this docker compose file
`networks :` THe type of network you want to use for your containers
`ports :` This defines the port mappings e.g. `3000:3000`. Note this is in the order host to container port mapping
`image :` Name of the image to be built
`args :` The environment variables to be used during the build
`context :` Where to look for dockerfile if you are going to build one or more dockerfiles which live in different folders. `.` would be used to represent dockerfile being in same directory as the docker-compose file.

### Volumes

* When a container is stopped it takes all of the files and data stored in that container with it
* Sometimes you may wish some of the data is retained e.g. log files
* A volume is a way to store data outside of the container
* This means you can write to the host directory rather than within the container itself

### Example

Example `docker-compose` file

```docker
version: "3.9"
services:
  web:
    build: .
    ports:
      - "5000:5000"
  redis:
    image: "redis:alpine"
    volumes:
      - ./logs:/var/www/logs

```
