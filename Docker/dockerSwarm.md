# Docker Swarm

- - - -

## Table of Contents

* [What is Docker Swarm?](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerSwarm.md#what-is-docker-swarm)
* [Definitions](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerCompose.md#definitions)
* [Commands](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerCompose.md#commands)

## What is Docker Swarm?

* Manages several Docker nodes
* These nodes can be virtual machines, cloud instances etc so long as they have Docker installed
* There are worker and manager nodes
* Can use Docker Swarm to quickly scale up replicas (instances of a Docker service)
* If a manager node sees a service is no longer running it will start a new instance to match the replica numbers expected

## Definitions

* __Docker Swarm:__  A cluster of Docker nodes (both manager and worker nodes)
* __Manager Node:__ A type of node which hosts control features (e.g. schedules, state, cluster stores etc)
* __Worker Node:__ A type of node which hosts Docker services and is controlled by manager nodes
* __Docker Service:__ A single microservice hosted in a container (e.g. web FE as part of a large application)

## Commands

Swarm has a series of commands which are only available when they are used as part of Docker Swarm

`docker service create --name <name> -p 8080:8080 --replicas 3 <imageName>` Spins up 3 replicas running the same image named

> When deciding on the number of manager nodes an odd number is preferred to avoid split brain situation
