# Docker Container Commands 🐳

Docker is a powerful platform for developing, shipping, and running applications inside containers. Containers are lightweight, isolated environments that package an application and its dependencies, making it easy to deploy and manage applications consistently across different environments.

# Table of Contents

1. [Creating Containers](#creating-containers-🏗️)
2. [Managing Containers](#managing-containers-📊)
3. [Inspecting Containers](#inspecting-containers-🔍)
4. [Logs and Executing Commands](#logs-and-executing-commands-📝💻)
5. [Removing Containers](#removing-containers-🗑️)
6. [Start New Container Interactively](#start-new-container-interactively)
7. [Run Additional Command in Existing Container](#run-additional-command-in-existing-container)


## Creating Containers 🏗️
To create and run a container from an image, use the command:

```bash
docker container run [Options] IMAGE [COMMANDS] [ARGS...]
```

This will pull the image from a registry if it is not available locally, and then create and start a container from it.

Some common options are:

- `--detach` or `-d`: Run the container in the background and print the container ID.
- `--publish` or `-p`: Publish a container's port(s) to the host. The format is `<host_port:container_port>`.
- `--name <container_name>`: Assign a name to the container.
- `--network <network_name>` or `--net`: Connect the container to a network.
- `--rm`: Automatically remove the container when it exits.
- `-it`: Run the container interactively.

For example, to run a container named `webserver` from the `nginx` image in the background and publish port 80 to port 8080 on the host, use the command:

```bash
docker container run --detach --publish 8080:80 --name webserver nginx
```

## Managing Containers 📊

Once containers are running, you can manage them with various commands:

- `docker container ps`: List all running containers.
- `docker container ps -a`: List all containers (including stopped ones).
- `docker container stop <container> ...`: Stop a running container.
- `docker container start <container> ...`: Start a stopped container.
- `docker container restart <container> ...`: Restart a container.
- `docker container pause <container> ...`: Pause a running container.
- `docker container unpause <container> ...`: Unpause a paused container.
- `docker container rm <container> ...`: Remove a stopped container.


## Inspecting Containers 🔍

- `docker container inspect <container>`: Display detailed information about a container.
- `docker container logs <container>`: Display the logs of a container.
- `docker container top <container>`: Display the running processes of a container.
- `docker container stats <container>`: Display a live stream of container resource usage statistics.


## Logs and Executing Commands 📝💻

To view container logs and execute commands inside a running container, you can use these commands:

- `docker container logs <container>`: Display the logs of a container.
- `docker container exec -it <container> <command>`: Execute a command inside a running container interactively.

Example:
```bash
docker container logs <container>
docker container exec -it <container> <command> (e.g. bash)
```

## Removing Containers 🗑️
To remove one or more containers, use the command:

```bash
docker container rm <id_of_container> <id>...
```

This will delete the containers from the docker system. The containers must be stopped before they can be removed.

Some common options are:
- `-f` or `--force`: Force remove a running container.

## Start new container interactively
To start a new container and attach an interactive shell to it, use the command:

```bash
docker container run -it IMAGE [COMMANDS] [ARGS...]
```

This will create and run a container from an image, and open a terminal session to it. You can use any commands inside the container as if you were logged into it.

The options are:

- `-t` or `--tty`: Allocate a pseudo-TTY.
- `-i` or `--interactive`: Keep STDIN open even if not attached.

For example, to start a new container from the `ubuntu` image and run a bash shell, use the command:

```bash
docker container run -it ubuntu bash
```

## Run additional command in existing container
To run an additional command in an existing container, use the command:

```bash
docker container exec -it <container_name> [COMMANDS] [ARGS...]
```

This will execute a command in a running container and attach an interactive shell to it. You can use any commands inside the container as if you were logged into it.

The options are:

- `-t` or `--tty`: Allocate a pseudo-TTY.
- `-i` or `--interactive`: Keep STDIN open even if not attached.

For example, to run a bash shell in an existing container named `webserver`, use the command:

```bash
docker container exec -it webserver bash
```

Docker provides a rich set of commands and options to manage containers effectively. 🚀