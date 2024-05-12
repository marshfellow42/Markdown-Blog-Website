---
layout: post
title: How to create a Private Git Server on a Raspberry Pi
categories: how-to
permalink: /how-to-create-a-private-git-server-on-a-raspberry-pi/
---

For this Private Git Server, we're gonna use Gitea

Why Gitea instead of GitLab?

Well, Gitea is more lightweight and only contains the essential for a Git server like that

## Installation
To install Gitea, we're going to use docker-compose

Download and run the docker installation script:

```bash
curl -fsSL https://get.docker.com -o install-docker.sh
sudo sh install-docker.sh
```
Add the current user to the “docker” group to enable commands to be run without sudo. Replace “pi” with your username if it differs. Lot out and back in to apply changes.

```bash
sudo usermod -aG docker pi
sudo su – pi
```
Check that docker and docker compose have been installed:

```bash
docker --version
docker compose version
```

Check your UID and your GID, this'll be useful for later

```bash
id -u <username>
id -g <username>
```
Create a ```docker-compose.yml``` file somewhere sensible and paste in the following. Remember to change the ports if there are clashes with other services. If you already have

```bash
version: "3"

networks:
  gitea:
    external: false

services:
  server:
    image: gitea/gitea:latest
    container_name: gitea
    environment:
      - USER_UID=1000
      - USER_GID=1000
    restart: always
    networks:
      - gitea
    volumes:
      - ./gitea:/data
      - /etc/timezone:/etc/timezone:ro
      - /etc/localtime:/etc/localtime:ro
    ports:
      - "3000:3000"
      - "222:22"
```
Save and exit your editor. If you want to start docker when your Pi boots up, then run the following command:

```bash
sudo systemctl enable docker
```
Now start the docker stack. Run the following command (in the directory of your docker-compose.yml file) to start the containers in the background:

```bash
docker compose up --detach
```
Now you can navigate to your Gitea server by pointing your web browser to the IP address of your Raspberry Pi followed by port 3000.