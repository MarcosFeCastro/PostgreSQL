# PostgreSQL

### Docker - [Docker Hub](https://hub.docker.com/_/postgres)
```
$ docker network create postgres
$ docker volume create postgres
$ docker volume create pgadmin

$ docker run -d --rm -p 5432:5432 --name postgres --net postgres -v postgres:/var/lib/postgresql/data -e POSTGRES_PASSWORD=postgres postgres:14-alpine
$ docker run -d --rm -p 15432:80 --name pgadmin --net postgres -v pgadmin:/var/lib/pgadmin -e PGADMIN_DEFAULT_EMAIL=admin@postgres.com -e PGADMIN_DEFAULT_PASSWORD=postgres dpage/pgadmin4
```

### Docker Compose
```
$ docker-compose --profile db up --build
```

# [On Kubernetes](kubernetes/README.md)