# SETUP

Context : using ubuntu 23 and need to install SQL Server 2022 was not possible because SQL Server was not available for Ubuntu 23, i decided to install it with Docker.

https://learn.microsoft.com/fr-fr/sql/linux/quickstart-install-connect-docker?view=sql-server-ver16&pivots=cs1-bash

## Get image
```shell
sudo docker pull mcr.microsoft.com/mssql/server:2022-latest
```

## Start instance

Start
```
docker run \
   --env "ACCEPT_EULA=Y" --env "MSSQL_SA_PASSWORD=<YourStrong@Passw0rd>" \
   --publish 1433:1433 --name sqlserver --hostname sqlserver \
   --detach \
   mcr.microsoft.com/mssql/server:2022-latest
```

Check it is running
```
docker container ps
docker container logs sqlserver
```

