---
title: "Docker Quickstart"
date: 2020-12-06T15:25:19+05:30
publishdate: 2020-12-06T11:17:14+05:30
lastmod: 2020-12-06T18:55:29+05:30
tags: ["DevOps","Containers","Docker"]
type: "post"
comments: false
---

## Introduction

Hello everyone!

As a pentester by profession, I usually have to deal with different environments. Sometimes compiling tools which has some nasty dependencies and failing to build or want to generate a poc for specific environment or creating CTFs. Docker always comes handy in such situations. So here is beginners guide on how to start with docker and get some familiarity with the commands.

---

## What is Docker?
Docker is an opensource tool used to easily deploy applications in sandbox environments called *containers*. In a docker container we can run different tools to do specific job. 

---

## What is Container?
Container is standard unit of softeare that packages up the code and dependencies so that application runs quickly and reliably from one machine to another. Containers are small, fast, and portable because unlike a virtual machine, containers do not need include a guest OS in every instance and can, instead, simply leverage the features and resources of the host OS.

---

## Containers vs VM

![containers-vm](/images/blog/containers-101.png "Containers-VM")

A virtual machine (VM) is an emulation of a computer system. It makes it possible to run what appear to be many separate computers on hardware that is actually one computer. The operating systems (OS) and their applications share hardware resources from a single host server, or from a pool of host servers.

With containers, instead of virtualizing the underlying computer like a virtual machine (VM), just the OS is virtualized.

Containers sit on top of a physical server and its host OS — typically Linux or Windows. Each container shares the host OS kernel and, usually, the binaries and libraries, too. Shared components are read-only. At a high level, Docker is a Linux utility that can efficiently create, ship, and run containers.

---

## Why Containers?

![why-containers](/images/blog/why-containers.png "Why Containers")

Docker solves multiple problem. You must have always heard the developers arguing about the code which works at their system but always fail to work in production environment. Container solves following mentioned problems which  [Julia Evans](https://twitter.com/b0rk "Julia Evans") has mentioned precisely in her [zines](https://wizardzines.com/ "Zines"). (I recommend everyone to check her awesome work)

1. Dependency issues in building softwares
2. Issues in deploying softwares


---

## Docker Terminology

#### Images

The blueprints of our application which form the basis of containers. A package with all the dependencies and information needed to create a container. An image includes all the dependencies (such as frameworks) plus deployment and execution configuration to be used by a container runtime.

#### Containers

An instance of a Docker image. A container represents the execution of a single application, process, or service. It consists of the contents of a Docker image, an execution environment, and a standard set of instructions.

#### Docker Daemon

Background service running on the host that manages building, running and distributing Docker containers.

#### Docker Client

The command line tool that allows the user to interact with the daemon.

#### Docker Hub 

A public registry to upload images and work with them. Docker Hub provides Docker image hosting, public or private registries, build triggers and web hooks, and integration with GitHub and Bitbucket.

---

## Docker Architecture
![docker-arch](/images/blog/docker-arch.png "Docker Architecture")

---

## Examples

I know you are bored now reading all the internal stuff mentioned. Let's make things bit exciting. Let's start with some practicle examples and understand few commands.

##### Hello world

![hello-world](/images/blog/1-hello-world.png "Hello-World")

`$ docker run hello-world`

Above command will run hello-world image which is specifically designed for understanding the docker flow.

##### Pulling Docker images from DockerHub

![docker-pull](/images/blog/2-docker-pull.png "Docker-pull")

`$ docker pull busybox`

The pull command fetches the busybox image from the Docker registry and saves it to our system

##### List Docker Images

![docker-pull](/images/blog/3-docker-image.png "Docker-images")

`$ docker images`

Use the docker images command to see a list of all images on your system.


##### Running Docker Containers

![docker-run](/images/blog/4-docker-run.png "Docker-run")

`$ docker run busybox`

Docker client finds the image, loads up the container and then runs a command in that container.

![docker-run-2](/images/blog/5-docker-run-2.png "Docker-run-2")

`$ docker run busybox echo "hello from busk3r"`

When we run docker run, we didn't provide a command, so the container booted up, ran an empty command and then exited. To run a command inside container fire above command.


##### Listing Docker Containers

![docker-ps-1](/images/blog/6-docker-ps-1.png "Docker-ps-1")

`$ docker ps`

The docker ps command shows you all containers that are currently running.

![docker-ps-2](/images/blog/7-docker-ps-2.png "Docker-ps-2")

`$ docker ps -a`

Above command will list of all containers that we ran.

##### Getting shell inside Container 

![docker-run-it](/images/blog/8-run-it.png "Docker-run-it")

`$ docker run -it busybox sh`

Running the run command with the -it flags attaches us to an interactive tty in the container. We can run multiple commands in shell.

##### Deleting Containers 

![docker-rm](/images/blog/9-docker-rm.png "docker-rm")

`$ docker rm <id>`


##### Deleting Containers when stopping containers

![docker-rm](/images/blog/11-docker-rm.png "docker-rm")

`$ docker run -it --rm busybox sh`

Delete the docker images when exit with --rm

##### Deleting Images

![docker-rmi](/images/blog/10-docker-rmi.png "docker-rmi")

`$ docker rmi busybox`

To delete Image first delete all the containers associated with image and run above command.

---

##Conclusion:
The blog post is a beginner's guide for quickstart on how to work with docker. Get your hands dirty and get going. I enjoyed writing this article and hope that you enjoyed reading it.

Hack the planet :-)

---

## References:
1. https://www.backblaze.com/blog/vm-vs-containers/
2. https://wizardzines.com/
3. https://docs.microsoft.com/en-us/dotnet/architecture/microservices/container-docker-introduction/docker-terminology
4. https://docs.docker.com/get-started/overview/