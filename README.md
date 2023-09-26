# Docker Basics README 🐳

Docker is a platform for developing, shipping, and running applications in containers. Containers are lightweight, isolated environments that encapsulate an application and its dependencies, ensuring consistency across different environments.

## Getting Started 🚀

To start using Docker, follow these simple steps:

1. **Installation**:

   Install Docker on your machine by visiting the [official Docker website](https://docs.docker.com/get-docker/) and following the installation instructions for your operating system.

2. **Hello World**:

   Run your first Docker container with the classic "Hello World" example to ensure Docker is correctly installed:

   ```bash
   docker run hello-world
   ```

   This command will download and run a minimal container, and you should see a message confirming a successful installation.

## Basic Docker Commands 📋

Here are some essential Docker commands to get you started:

- **`docker run`**: Create and start a container from an image.
- **`docker ps`**: List all running containers.
- **`docker images`**: List all locally available Docker images.
- **`docker pull`**: Download an image from Docker Hub.
- **`docker stop`**: Stop a running container.
- **`docker rm`**: Remove a stopped container.
- **`docker rmi`**: Remove an image.
- **`docker exec`**: Execute a command in a running container.

## Dockerfile 🐋

A Dockerfile is a script that defines how to build a Docker image. It includes instructions for installing dependencies, configuring the environment, and specifying what command to run when the container starts. Create a Dockerfile in your project directory to define your application's container.

Here's a simple example of a Dockerfile for a Node.js application:

```Dockerfile
# Use an official Node.js runtime as a base image
FROM node:14

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application source code
COPY . .

# Expose a port for the application
EXPOSE 3000

# Define the command to run the application
CMD ["node", "app.js"]
```

## Docker Compose 🚢

[Docker Compose](https://docs.docker.com/compose/) is a tool for defining and running multi-container Docker applications. You can use a `docker-compose.yml` file to specify the services, networks, and volumes for your application's containers.

## Resources 📚

For more in-depth information and documentation, visit the official [Docker Documentation](https://docs.docker.com/).

That's it! You've covered the basics of Docker. Explore further to leverage Docker's power for your development and deployment needs. 🌟