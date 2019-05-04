[![Build Status](https://travis-ci.org/wizardstech/docker.svg?branch=master)](https://travis-ci.org/wizardstech/docker)

# Supported tags and respective Dockerfile links

## Simple Tags

* [1.12-alpine](https://github.com/wizardstech/docker/blob/master/gofresh/1.12/alpine/Dockerfile)

# Quick reference

-	**Where to get help**:
	[the Docker Community Forums](https://forums.docker.com/), [the Docker Community Slack](https://blog.docker.com/2016/11/introducing-docker-community-directory-docker-community-slack/), or [Stack Overflow](https://stackoverflow.com/search?tab=newest&q=docker)

-	**Where to file issues**:
	[https://github.com/wizardstech/docker/issues](https://github.com/wizardstech/docker/issues)

-	**Maintained by**:
	[Wizards Technologies](https://github.com/wizardstech)

-	**Source of this description**:
	[gofresh directory](https://github.com/wizardstech/docker/tree/master/gofresh) ([history](https://github.com/wizardstech/docker/commits/master))

-	**Supported Docker versions**:
	[the latest release](https://github.com/docker/docker-ce/releases/latest) (down to 1.6 on a best-effort basis)

# What is gofresh ?

The purpose of gofresh is to provide a container which include the [fresh](https://github.com/gravityblast/fresh) command line tool to improve development efficiency with golang.

You **should not** use this in production !

# How to use this image

## With docker-compose

Inside your project directory you must have theses two files

.env

```
...

WORKDIR=github.com/you_username/your_project
```

docker-compose.yml

```
version: '3'

services:
  app:
    image: wizardstech/gofresh:1.12-alpine
    working_dir: /go/src/${WORKDIR}
    environment:
      WORKDIR: $WORKDIR
    volumes:
      - .:/go/src/${WORKDIR}
```

Then, simply run `docker-compose up -d`, that's it !
