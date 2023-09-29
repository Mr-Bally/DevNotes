# Containerizing an app

- - - -

## Table of Contents

* [Docker file](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerOverview.md#docker-file)
* [Docker commands](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerOverview.md#docker-commands)
* [Definitions](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerOverview.md#definitions)

## Docker file

Docker file is a declarative set of instructions for how docker should build an app with its dependancies into a docker image

### Docker file common commands

`FROM` Pulls an existing image

`LABEL` Add meta data about the application

`RUN` Execute a command e.g. `mkdir`

`COPY` Copy files

`WORKDIR` Sets current working directory

`ENTRYPOINT` Starts the container

### Example Docker file

```docker
FROM node:12-alpine
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
```

## Docker commands

`docker image build -t <dockerHubId/repo:imageName> .` Builds a docker image in the current directory with the given tag

`docker image rm <image tag>` Removes a docker image with the given tag

`docker container run -d --name <container name> -p 8000:8080 <image name>` Run a container in detached mode (outside of terminal), name it, map port 8000 on the docker host to 8080 which the app is listening to

`docker container stop <container name>` Stops the container from running (will still remain in list of containers)

`docker container start <container name>` Starts a stopped container

`docker container rm <container name> -f` Removes container from list of containers using the force flag

`docker image push <image tag>` Pushes image to repository (Dockerhub by default)

> Note: Images are build time constructs whereas containers are run time constructs

## Definitions

* __Docker file:__ A file which defines how a Docker image should be build
* __Image:__ A build time construct which can be used to create a container
* __Container:__ A run time construct which is used to run an application in Docker
* __Containerizing an app:__ The process of running an application in a Docker container