# Docker Compose Documentation 🎶

Docker Compose is a tool designed to make it easier to define and share multi-container Docker applications. With Compose, you can create a Compose file to configure your application’s services, networks, and volumes. Then, using a single command, you can create and start all the services specified in the configuration.

## Why Use Docker Compose? 🤔
- **Configure Relationships:** Docker Compose allows you to configure relationships between containers, ensuring they work together as a unified whole.
- **Save Settings:** It helps in saving your Docker container run settings in an easy-to-read file, thus making your setup reproducible and easy to share.
- **One-liner Startup:** It enables one-liner developer environment startups, simplifying the process of starting your application with a single command.

## What Comprises Docker Compose? 🧩
Docker Compose is comprised of two separate but related things:
1. **YAML-formatted file:** This file describes your solution options for:
    - Containers
    - Networks
    - Volumes
2. **CLI tool (`docker-compose`):** This tool is used for local development and test automation with those YAML files.

## Understanding `docker-compose.yml` 📄
The `docker-compose.yml` file is where you define your application's services, networks, and volumes. Compose YAML format has its own versions such as 1, 2, 2.1, 3, 3.1.

- This YAML file can be used with the `docker-compose` command for local Docker automation or directly with Docker in production with Swarm (as of v1.13).
- The default filename is `docker-compose.yml`, but any filename can be used with the `-f` option in `docker-compose`.

### Example 📖
```yaml
version: '3.1'
services:  # containers
    servicename:  # container name (docker run --name)
        image:  # image (optional)
        command:  # startup command (optional)
        environment:  # environment variables (-e) (optional)
        volumes:  # volumes (-v) (optional)
    servicename2:
volumes:  # volumes (docker volume create) (optional)
networks:  # networks (docker network create) (optional)
```

### Example with `docker-compose` 📖
```yaml
version: '3'  # Version of Docker Compose syntax, '3' is the latest version as of now

services:  # Define the services your application is composed of
  web:  # Name of the first service
    image: nginx:latest  # Docker image to use for this service
    ports:  # Ports to expose
      - "8080:80"  # Map port 8080 on the host to port 80 in the container
    volumes:  # Mount host directories into the container
      - ./web-root:/usr/share/nginx/html  # Mount ./web-root directory to /usr/share/nginx/html in the container
    depends_on:  # Define dependencies between services
      - db  # This service depends on the db service

  db:  # Name of the second service
    image: postgres:latest  # Docker image to use for this service
    environment:  # Set environment variables in the container
      POSTGRES_USER: user  # Username for PostgreSQL
      POSTGRES_PASSWORD: password  # Password for PostgreSQL
    volumes:  # Mount host directories or named volumes
      - db-data:/var/lib/postgresql/data  # Create a named volume db-data to persist data

volumes:  # Define named volumes
  db-data:  # Name of the volume. This name can be used in the 'volumes' section of services

networks:  # Define networks
  default:  # Name of the network
    external: 
      name: my-network  # Name of an existing external network to connect to
```

## Docker Compose CLI 🖥️
Docker Compose CLI is installed along with Docker for Windows and is ideal for local development/testing but is not recommended for production.

### Common Commands 🛠️
- **Start Up:**
```bash
docker-compose up  # Set up volumes/networks and start all containers
```
- **Tear Down:**
```bash
docker-compose down  # Stop all containers and remove containers/volumes/networks
```

### Optional Commands 🛠️
- **Detached Mode:**
```bash
docker-compose up -d  # Run containers in the background
```

### Help and Other Commands 🛠️
```bash
docker-compose --help  # Get help on docker-compose

docker-compose ps  # List containers
docker-compose top  # Display running processes
```

With Docker Compose, orchestrating multi-container Docker environments becomes a breeze, thus empowering developers to focus more on building great applications. 🚀