# Install Docker from docs

1. What is Docker?
   Docker is a tool that uses containerization technology to isolate applications and their dependencies. Think of it as a virtual shipping container for your app that ensures it behaves the same way, whether it's on your local machine, a testing server, or a production server.

## Docker let's you do a lot of things

- It let's you containerize your applications.
- It let's you run other people's **code + packages** in your machine.
- It let's you run common software packages inside a container (for eg - Mongo, Postgres, etc)
- Think container as mini container running inside your computer

- Docker => containers => mini machines (has networks/filesystem)
- When I go to localhost:3000 it does not go to the code running in container, we an redirect the request coming in local to container.

## Where can we get packages from?

- Just like you push your code to Github/Gitlab.
- You can push **images** to **docker registries**

- Images are like CD
- Image has all the necessary things to run code

## Docker Image vs Docker Container

1. Docker Image

- What It Is: A read-only template that contains the application, its dependencies, and instructions to create a container.
- State: Static and immutable (does not change).
- Purpose: Acts as a blueprint for creating Docker containers.
- Storage: Exists as a file on disk or in a registry (like Docker Hub).

  > Usage:
  > Built using a Dockerfile.
  > Shared across teams and systems.
  > Does not execute directly; it’s just a base to spin up containers.

2. Docker Container

- What It Is: A runtime instance of a Docker image, including its filesystem, application code, and processes.
- State: Dynamic and mutable (can change at runtime).
- Purpose: Runs the actual application. You can start, stop, or delete a container.
- Storage: Ephemeral (changes made inside a container are lost unless persisted using volumes).
  > Usage:
  > Created and started from an image.
  > Isolated from the host system and other containers.
  > Multiple containers can be created from the same image.

![Docker Image](https://drive.google.com/uc?id=11hq8olusPU7rIQ0C3-t2P32k7_C810d3)

- You Bring image from Internet and start the container locally
- **Container** is just an **Image** in execution
- Example - I take the ubuntu in the CD/PD and install run in my machine. So what inside CD is image and running Ubuntu is the container

# Common commands to know

```sh
1. docker run

e.g. docker run mongo
```

```sh
2. docker ps
```

```sh
3. docker kill
```

## Adding a port mapping

```sh
docker run -p 27017:27017 mongo
```

## Starting in detached mode

Adding **-d** will ensure it starts in the background

```sh
docker run -d -p 27017:27017 mongo
```

## Inspecting a container

```sh
docker ps
```

this will show you all the containers you are running

## Stopping a container

```sh
docker kill <container_id>
```

Will stop the container that you are running

## Postgres

```sh
docker run -e POSTGRES_PASSWORD=mysecretpassword -d -p 5432:5432 postgres
```

The connection string for this postgres would be

```sh
postgresql://postgres:mysecretpassword@localhost:5432/postgres
```
