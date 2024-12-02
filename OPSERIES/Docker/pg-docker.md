# DOCKER PG IMAGE

Download and run a postgres image

Images can be found in docker hub https://hub.docker.com/_/postgres



```shell
docker run -d --name postgres-message-history -p 5432:5432 -e POSTGRES_PASSWORD=123456_ postgres POSTGRES_USER=admin
```

`docker start postgres-message-history`

`docker run -it --rm --network host postgres psql -h postgres-my-pg-name -U postgres`

