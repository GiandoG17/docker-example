# docker-example
Php 7.2 / Apache / Mailhog / MariaDb / Mongo Db / Portainer.

Docker example project by [GiandoG17](http://www.giandonatogreco.com)

# Useful links

+ [Get started with Docker Desktop for Mac](https://docs.docker.com/docker-for-mac/)
+ [Docker command line](https://docs.docker.com/engine/reference/commandline/cli/)
+ [Overview of docker-compose CLI](https://docs.docker.com/compose/reference/overview/)

# What are we going to create?

+ [Nginx proxy - JWILDER](https://github.com/jwilder/nginx-proxy)
+ [MariaDb](https://hub.docker.com/_/mariadb)
+ [MongoDb](https://hub.docker.com/_/mongo)
+ [MailHog - Web and API based SMTP testing](https://github.com/mailhog/)
+ [Portainer - Manage and support your Docker environments](https://www.portainer.io/)
+ Test ENV


## Commands

List containers

```bash
docker ps
```
Restart one or more containers

```bash
docker restart <container>
```

Stop running container without removing them.

```bash
docker stop <container>
```
Remove one or more containers
+ -f = force

```bash
docker rm <container>
```
Run a command in a running container

```bash
docker exec -ti <container> bash
```

List images

```bash
docker image ls
```
Builds, (re)creates, starts, and attaches to containers for a service.
+ --build = Build images before starting containers.
+ -d = Detached mode: Run containers in the background, print new container names

```bash
docker-compose up
```
Stops containers and removes containers, networks, volumes, and images created by up.

```bash
docker-compose down
```

## Be careful
There are many useful commands to better manage your containers, visit the links above to view the official docker documentation.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
