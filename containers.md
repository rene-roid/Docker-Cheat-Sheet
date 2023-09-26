# Docker Container Commands 🐳

Docker is a powerful platform for developing, shipping, and running applications inside containers. Containers are lightweight, isolated environments that package an application and its dependencies, making it easy to deploy and manage applications consistently across different environments.

## Creating Containers 🏗️

To create a Docker container, you can use the `docker run` command. Here are some of the commonly used options:

- `-d, --detach`: Run the container in the background.
- `--name <name>`: Assign a custom name to the container.
- `-p, --publish <host_port>:<container_port>`: Map a port from the host to the container.
- `--network <network>`: Connect the container to a specific Docker network.
- `--rm`: Automatically remove the container when it exits.

Example:
```bash
docker container run -d --name my_container -p 3000:3000 --network my_network nginx:latest
```

## Managing Containers 📊

Once containers are running, you can manage them with various commands:

- `docker container ps`: List all running containers.
- `docker container ps -a`: List all containers (including stopped ones).
- `docker container stop <container>`: Stop a running container.
- `docker container start <container>`: Start a stopped container.
- `docker container restart <container>`: Restart a container.
- `docker container pause <container>`: Pause a running container.
- `docker container unpause <container>`: Unpause a paused container.
- `docker container rm <container>`: Remove a stopped container.

Example:
```bash
docker container stop my_container
```

## Inspecting Containers 🔍

You can inspect container details using the `docker container inspect` command:

- `docker container inspect <container>`: Display detailed information about a container.

Example:
```bash
docker container inspect my_container
```

## Logs and Executing Commands 📝💻

To view container logs and execute commands inside a running container, you can use these commands:

- `docker container logs <container>`: Display the logs of a container.
- `docker container exec -it <container> <command>`: Execute a command inside a running container interactively.

Example:
```bash
docker container logs my_container
docker container exec -it my_container bash
```

## Removing Containers 🗑️

To remove containers, you can use the `docker container rm` command. Be cautious, as this action is irreversible.

Example:
```bash
docker container rm my_container
```

Docker provides a rich set of commands and options to manage containers effectively. By understanding and using these commands, you can harness the full power of Docker for containerized application development and deployment. 🚀