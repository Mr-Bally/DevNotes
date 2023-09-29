# Docker Overview

- - - -

## Table of Contents

* [What are containers?](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerOverview.md#what-are-containers)
* [Why shoould you use containers?](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerOverview.md#why-should-you-use-containers)
* [Simple lifecycle](https://github.com/Mr-Bally/DevNotes/blob/main/Docker/dockerOverview.md#simple-lifecycle)

## What are containers?

* In Docker, applications run in containers
* Containers are lightweight and contain all the code and dependancies an application needs to run
* Can host multiple containers on the same physical or virtual host

## Why should you use containers?

* Containers run on a virtualised OS rather than virtualised hardware like a VM
* Each container has its own process tree and root file system
* Every container on the same host share the same OS kernel
* Very low overhead when compared with a traditional CVM
* You can deploy many containers to the same host

## Simple lifecycle

1. Create source code
2. Use docker to create an image of the code
3. Use the image to create a container
4. The container runs the application