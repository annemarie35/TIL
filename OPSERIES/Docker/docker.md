# DOCKER

## Images

List images on your machine
```shell
docker images
```

Then remove images given its id
```shell
docker rmi image-id
````

You may also find that you have stopped containers that are causing the lock. Remove these first using:

```shell
docker rm  $(docker ps -q -a)
```

```shell
docker container ls -a
```

List all Docker containers, both running and stopped, on the system.
`docker ps -a`

ps : process status [doc](https://docs.docker.com/engine/reference/commandline/ps/)
a : means --all
--quiet or	-q : Only display container IDs

### Remove unused images 
```shell
docker image prune --all --force
```
See [documentation](https://docs.docker.com/reference/cli/docker/system/prune/#extended-description) for prune and that [stackoverflow](https://stackoverflow.com/questions/44785585/how-can-i-delete-all-local-docker-images) conversation


### Remove all unused containers :
```shell
docker system prune
```

This will remove:
- all stopped containers
- all networks not used by at least one container
- all dangling images
- unused build cache


### List all containers 
```shell
docker container list -a
```

# Docker compose


Example 
```yaml
version: "1.0"

services:
  sql-server-db:
    container_name: sql-server-db
    image: mcr.microsoft.com/mssql/server:2022-latest
    ports:
      - "1433:1433"
    environment:
      MSSQL_SA_PASSWORD: "<YourStrong@Passw0rd>"
      ACCEPT_EULA: "Y"
```

# Difference between docker-compose and Dockerfile

`docker-compose build` use DockerFile to build image
`docker-compose up -d`run docker image

## PB TLS 
docker https://stackoverflow.com/questions/71527736/c-sharp-sslexception-ssl-handshake-failed-with-openssl-error-ssl-error-ssl


- https://blog.logrocket.com/docker-sql-server/
- https://github.com/GradedJestRisk/db-training/blob/master/RDBMS/SQLServer/restore-backup.md

# FAQ
- How to install a specific Node.js version in an alpine Docker image ?
Example in the first line of this docker file 
```
FROM node:20.10-alpine

# Installing libvips-dev for sharp Compatibility
RUN apk update && apk add --no-cache build-base gcc autoconf automake zlib-dev libpng-dev nasm bash vips-dev git
#ARG NODE_ENV=development
#ENV NODE_ENV=${NODE_ENV}

WORKDIR /opt/
COPY package.json package-lock.json ./
RUN npm install -g node-gyp
RUN npm config set fetch-retry-maxtimeout 600000 -g && npm install
ENV PATH /opt/node_modules/.bin:$PATH

WORKDIR /opt/app
COPY . .
RUN chown -R node:node /opt/app #&& chmod -R 777 /opt
USER node
RUN ["npm", "run", "test"]
RUN ["npm", "run", "format"]
RUN ["npm", "run", "lint"]
RUN ["npm", "run", "build"]
EXPOSE 3000
CMD ["npm", "run", "start:dev"]
```

- Which network ?
`docker network ls` 