---
layout: post
title: Containers - Concepts and Implementation.
permalink: /devops/containers
author: pranav
support_data: {
      links: { "https://en.wikipedia.org/wiki/Virtualization": "Virtualization Wiki",
               "https://docs.docker.com/":"Docker Official Docs",
               "https://docs.openshift.com/container-platform/3.3/architecture/core_concepts/containers_and_images.html":"Open shift docs"
                },
      tags: {"containers", "docker"},
      categories: {"devops"},
      }
---

## Virtualization
Well, it means to create something or anything which doesn't really exists, but the entity which for which it is done
believes it is there. For example, in the movie matrix, humans are given a virtual environment to live. That would be
called as virtualization of Earth maybe. But yeah the concept is same for what we do for python environments, Vagrant,
Containers and else where. The difference lies in the level of virtualization we do. Virtualization can be done on a 
hardware level, Desktop level, operating system level, and many others which can be found in the Virualization wiki link.

In this post I would like to discuss operating system level virtualization which is achieved with containers.

## Containers
Containers are like we think, can be packed with some things and can be transferred over to different places. The operating
system containers are same in terms that a software is packed in them and the process is executed with proper commands in 
the container specific isolated environment.

For example, if I have a mongodb container, that would contain

1. Mongo db Software
2. Software to run mongo, for example data directories needed '/data/db'.
3. Naming, ports and other services.

A container is specifically designed to run a particular process, and no more. This means at a time, only 1 process would run in the container. Docker containers are extended version of chroot functionality, as they extend the functionality of 
linux containers with git-like image packaging, richer and easier cli and image sharing platform. The "images" that I am referring to can be understood as form an image you can create multiple containers. Images are like a sitemap/plan for building and running containers. You can create a container from an image, modify it in your own needs and pack it into a new image for reproduction by different users.


## Regarding Docker Containers

I am briefly touching some points that I learnt during my project, and they would explain the features of docker. For more details you can always visit the official docs.

1. Docker CLI - Docker cli is really useful and efficient tool to manage the image, containers, running containers, stopping them and what else. Almost all the actions can be done using this tool.

2. Docker Images - You can list all the docker images using `docker images` command. You can pull images (like git pull) using `docker pull imagename`, and in the same manner you can commit new images using `docker commit`. Each image has a tag, a name, an a hash. You can refer to an image using hash and name:tag format. Tag is generally used to differentiate between different versions of same images. Refer to the official docs for more details as you would be working with them.

3. DockerFile - It is a build file. It acts as a script to build docker images and also helps to make custom changes to that image (like attaching storage, pulling base image) in itself. So what developers can do is share images using dockerfiles, at the same time keeping their image confidential. Dockerfile has a proper syntax, and semantics. So review them on the docs.

Few points that I haven't touched but are useful - docker-compose, docker swarm. I will update this as I use docker more.