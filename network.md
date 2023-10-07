# Docker Network CLI Commands 🌐

Docker networks allow containers to communicate with each other, both within the same host and across different hosts. They provide isolation and flexibility in defining how containers interact with each other. Let's explore the Docker network commands and their options:

# Table of Contents

1. [Container Networking](#container-networking-🌐)
    1. [Public Communication](#public-communication-🌐)
    2. [Private Communication](#private-communication-🌐)
2. [Creating Networks](#creating-networks-🏗️)
3. [Listing Networks](#listing-networks-📋)
4. [Inspecting Networks](#inspecting-networks-🔍)
5. [Connecting Containers](#connecting-containers-🌐)
6. [Disconnecting Containers](#disconnecting-containers-🚫)
7. [Removing Networks](#removing-networks-🗑️)

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
docker network create <name> --driver bridge --subnet <subnet> (eg. 172.18.0.0/16) --gateway <gateway> (eg. 172.18.0.1)
```

## Listing Networks 📋

To list all available networks, you can use the `docker network ls` command.

Example:
```bash
docker network ls
```

Options:

- `-f, --filter <filter>`: Filter output by network properties. For example, `docker network ls -f name=<network>` will only list the network named `<network> (eg. my_network)`.

## Inspecting Networks 🔍

To view details about a specific network, use the `docker network inspect` command:

Example:
```bash
docker network inspect <network>
```

Options:

- `-f, --format <format>`: Specify the output format (json or text).
- `-q, --quiet`: Only print the network ID.


## Connecting Containers 🌐

To connect a container to a network, you can use the `docker network connect` command:

To connect a container to a network, you can use the docker network connect command:

Options:

- `-f, --force`: Force the container to connect to the network, even if it is already running.
- `-l, --link <container>`: Link the container to another container on the same network.

Example:
```bash
docker network connect <network> <container>
```

## Disconnecting Containers 🚫

To disconnect a container from a network, use the `docker network disconnect` command:

Example:
```bash
docker network disconnect <network> <container>
```

## Removing Networks 🗑️

To remove a Docker network, you can use the `docker network rm` command:

Options:
- `-f, --force`: Force the network to be removed, even if it is in use by containers.

Example:
```bash
docker network rm <network>
```

Docker networks play a crucial role in container orchestration, enabling you to create complex and scalable applications. 🚀