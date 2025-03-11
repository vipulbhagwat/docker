# Docker Cheatsheet

## 🐳 Docker Basics

### Install & Setup
```sh
# Install Docker (Linux)
sudo apt install docker.io   # Ubuntu/Debian
sudo yum install docker     # CentOS/RHEL

# Start Docker daemon
sudo systemctl start docker
sudo systemctl enable docker

# Verify installation
docker --version
docker info
```

### Manage Docker as a Non-Root User
```sh
sudo usermod -aG docker $USER
newgrp docker
```

## 🔍 Working with Containers

### Run & Manage Containers
```sh
# Run a container (interactive mode)
docker run -it ubuntu /bin/bash

# Run a container (detached mode)
docker run -d --name my_container nginx

# List running containers
docker ps

# List all containers (including stopped ones)
docker ps -a

# Stop a running container
docker stop my_container

# Remove a container
docker rm my_container
```

### Logs & Exec
```sh
# View container logs
docker logs my_container

# Attach to a running container
docker attach my_container

# Execute a command inside a container
docker exec -it my_container /bin/sh
```

## 🏗️ Working with Images

### Pull & Build Images
```sh
# Pull an image from Docker Hub
docker pull nginx

# Build an image from a Dockerfile
docker build -t my_image .
```

### Manage Images
```sh
# List images
docker images

# Remove an image
docker rmi nginx
```

## 📦 Working with Volumes
```sh
# Create a volume
docker volume create my_volume

# List volumes
docker volume ls

# Mount a volume to a container
docker run -d -v my_volume:/data nginx
```

## ⚙️ Networking
```sh
# List networks
docker network ls

# Create a network
docker network create my_network

# Connect a container to a network
docker network connect my_network my_container
```

## 🐙 Docker Compose
```sh
# Start services
docker-compose up -d

# Stop services
docker-compose down
```

## 🛠️ Docker System Cleanup
```sh
# Remove all stopped containers
docker container prune

# Remove all unused images
docker image prune -a

# Remove all unused volumes
docker volume prune
```

### 🔗 Useful References
- [Docker Docs](https://docs.docker.com/)


