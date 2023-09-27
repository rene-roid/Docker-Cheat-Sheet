# Docker Network CLI Commands 🌐

Docker networks allow containers to communicate with each other, both within the same host and across different hosts. They provide isolation and flexibility in defining how containers interact with each other. Let's explore the Docker network commands and their options:

## Container Networking 🌐

Containers can communicate with the outside world through public networks. By default, they can access external services, making them suitable for internet-facing applications.

### Private Communication 🌐

Containers can also communicate privately with each other using Docker's built-in networking features. This is useful for microservices architectures and internal communication.


## Creating Networks 🏗️

To create a Docker network, you can use the `docker network create` command. Here are some essential options:

- `<name>`: Assign a custom name to the network.
- `--driver <driver>`: Specify the network driver (default is 'bridge').
- `--subnet <subnet>`: Define a custom subnet for the network.
- `--gateway <gateway>`: Set a custom gateway for the network.

Example:
```bash
docker network create <name> --driver bridge --subnet 172.18.0.0/16 --gateway 172.18.0.1 my_network
```

## Listing Networks 📋

To list all available networks, you can use the `docker network ls` command.

Example:
```bash
docker network ls
```

## Inspecting Networks 🔍

To view details about a specific network, use the `docker network inspect` command:

Example:
```bash
docker network inspect my_network
```

## Connecting Containers 🌐

To connect a container to a network, you can use the `docker network connect` command:

Example:
```bash
docker network connect my_network my_container
```

## Disconnecting Containers 🚫

To disconnect a container from a network, use the `docker network disconnect` command:

Example:
```bash
docker network disconnect my_network my_container
```

## Removing Networks 🗑️

To remove a Docker network, you can use the `docker network rm` command:

Example:
```bash
docker network rm my_network
```

Docker networks play a crucial role in container orchestration, enabling you to create complex and scalable applications. By mastering these commands and options, you can efficiently manage container networking for your Dockerized applications. 🚀