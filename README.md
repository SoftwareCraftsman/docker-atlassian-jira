# README

[![](https://badge.imagelayers.io/softwarecraftsmen/atlassian-jira-software:latest.svg)](https://imagelayers.io/?images=softwarecraftsmen/atlassian-jira-software:latest)


## Prepare a docker host

```sh
docker-machine create --driver virtualbox atlassian <1>
docker-machine start atlassian <2>
eval `docker-machine env atlassian` <3>
```

1. Create a docker machine (once only)
2. Start the docker machine
3. Setup the docker client to use the docker-machine

## Build the image

```sh
docker build -t softwarecraftsmen/atlassian-jira-software .
```

## Run a JIRA instance

```sh
docker pull softwarecraftsmen/atlassian-jira-software
docker run -d --name jira -p 8080:8080 softwarecraftsmen/atlassian-jira-software
```

Startup after creating a container takes some time as the installation and configuration process is continuing.
So be patient until the start page for license registration can be opened.

To open the JIRA start page on Mac OSX run from the shell:
```sh
open http://`docker-machine ip atlassian`:8080
```
