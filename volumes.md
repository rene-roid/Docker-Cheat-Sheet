# Docker Volume and Bind Mounting Documentation 📦

Docker provides robust solutions for managing persistent data generated by and used by Docker containers. Volumes and bind mounts are two of the mechanisms that Docker provides for this purpose. While volumes are managed by Docker and are easy to share among containers, bind mounts are dependent on the host filesystem's directory structure.

# Table of Contents

1. [Volumes](#volumes-📦)
    - [Creating Volumes](#creating-volumes-🛠️)
    - [Listing Volumes](#listing-volumes-📋)
    - [Removing Volumes](#removing-volumes-🗑️)
    - [Using Volumes with Containers](#using-volumes-with-containers-🔄)
2. [Bind Mounts](#bind-mounts-🔗)
    - [Creating Bind Mounts](#creating-bind-mounts-🔗)
    - [Using Bind Mounts with Containers](#using-bind-mounts-with-containers-🔄)

## Volumes 📦
Volumes are the preferred mechanism for persisting data generated by and used by Docker containers. They are managed by Docker and can exist independently of the life of a container. Volumes are easy to back up or restore and can be shared and reused among containers. They are stored outside of the container filesystem, and their contents are preserved even if the container is removed.

### Creating Volumes 🛠️

To create a volume, use the command:

```bash
docker volume create [OPTIONS] [VOLUME_NAME]
```

Some common options are:

- `--driver` or `-d`: Specify volume driver name.
- `--label`: Set metadata for a volume.
- `--opt`: Set driver specific options.

For example, to create a volume named `my_volume` with the `local` driver, use the command:

```bash
docker volume create --driver local my_volume
```

### Listing Volumes 📋

To list all volumes:

```bash
docker volume ls [OPTIONS]
```

Some common options are:

- `--filter`: Provide a filtering option.
- `--format`: Format the output using the given Go template.

For example, to list all volumes that are dangling:

```bash
docker volume ls --filter dangling=true
```

### Removing Volumes 🗑️

To remove one or more volumes:

```bash
docker volume rm [OPTIONS] VOLUME [VOLUME...]
```

Some common options are:

- `--force` or `-f`: Force the removal of one or more volumes.

For example, to forcibly remove a volume named `my_volume`:

```bash
docker volume rm --force my_volume
```

### Using Volumes with Containers 🔄

To use a volume with a container:

```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

Some common options for volumes are:

- `--volume` or `-v`: Bind mount a volume (format: `[VOLUME_NAME]:[PATH_IN_CONTAINER]`).

For example, to run a container named `my_container` using the `my_volume` volume:

```bash
docker run -d --name my_container -v my_volume:/data IMAGE
```

## Bind Mounts 🔗
Bind mounts have limited functionality compared to volumes but are very performant. A bind mount allows you to mount a directory or a file from the host into the container. It relies on the host machine's filesystem having a specific directory structure available. Bind mounts are dependent on the host machine's directory structure, and the data in bind mounts is accessed directly from the host machine's filesystem.

### Creating Bind Mounts 🔗

To create a bind mount, specify the host path and container path when you run a container:

```bash
docker run [OPTIONS] -v [HOST_PATH]:[CONTAINER_PATH] IMAGE [COMMAND] [ARG...]
```

For example, to create a bind mount between `/host/data` and `/container/data`:

```bash
docker run -d -v /host/data:/container/data IMAGE
```

### Using Bind Mounts with Containers 🔄

The syntax for using bind mounts with containers is the same as creating them. Here's an additional example, running a container named `my_bind_container` with a bind mount:

To set the mount to the current directory use `${PWD}:[CONTAINER_PATH]`

```bash
docker run -d --name my_bind_container -v /host/data:/container/data IMAGE
```

With these commands and options, you can effectively manage persistent data in your Docker containers. 🚀