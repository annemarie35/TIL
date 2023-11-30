# DOCKER

## Images

List images on your machine `docker images`
Then remove images `docker rmi image-id`

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