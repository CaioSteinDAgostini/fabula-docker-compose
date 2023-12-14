# What is it?

This docker-compose packs toghether the Fabula (blog like demo application):
- backend with Spring Boot [Fabula](https://github.com/CaioSteinDAgostini/fabula)
- frontend with Angular [FabulaUI](https://github.com/CaioSteinDAgostini/fabulaUi)


# The images

The docker compose considers that you have already built the images, as described on each of the project's README, using their dockerfiles

# How to execute it

## The backend

```bash
mvn clean package
docker build --tag=fabula:latest
```

## The frontend

```bash
docker build --tag=fabula-ui:latest
```

## Composing

In order to verify the images are available, run (in terminal):
```bash
docker image ls

REPOSITORY                                TAG       IMAGE ID       CREATED         SIZE
fabula                                    latest    f6bf0736223f   2 hours ago     377MB
fabula-ui                                 latest    18199333f630   8 hours ago     189MB

```

and then...

```bash
docker compose up
```

The backend will listen at http port 8080, while the frontend will listen at http port 80, behing an Nginx instance.
