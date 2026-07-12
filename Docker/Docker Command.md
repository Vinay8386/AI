# Docker Commands

## Verify Docker
These commands confirm that Docker is installed correctly and that the Docker daemon is running and accessible from your terminal.

```bash
docker version
docker info
```

The first command shows the installed client and server versions, while the second gives detailed runtime information about the Docker environment.

---

## Images
These commands help you download, list, and remove container images from your local Docker environment.

```bash
docker pull <image_name>

docker images
docker image ls

docker rmi <image_name>
docker rmi <image_id>
```

`docker pull` downloads an image from a registry, `docker images` lists the images already available locally, and `docker rmi` removes images you no longer need.

---

## Containers
These commands let you create, manage, inspect, and interact with running containers.

```bash
docker run [OPTIONS] IMAGE_NAME

docker run -d --name <container_name> IMAGE_NAME

docker run -d --name flowise -p 3000:3000 flowiseai/flowise

docker run -d --name flowise -p 3000:3000 -v flowise_data:/root/.flowise flowiseai/flowise

docker ps
docker ps -a

docker start <container_name>

docker stop <container_name>

docker restart <container_name>

docker rm <container_name>

docker rm -f <container_name>

docker inspect <container_name>

docker logs <container_name>

docker logs -f <container_name>

docker exec -it <container_name> bash

docker exec -it <container_name> sh
```

`docker run` starts a new container from an image, `docker ps` shows active containers, and `docker exec` allows you to enter a running container for troubleshooting or manual commands.

---

## Docker Volumes
These commands manage persistent storage that containers can use to store data independently of the container lifecycle.

```bash
docker volume create <volume_name>

docker volume ls

docker volume inspect <volume_name>

docker volume rm <volume_name>
```

Volumes are used to preserve data across container restarts and removals, making them ideal for databases and application state.

---

## Docker Networks
These commands help you inspect, create, and remove Docker networks that allow containers to communicate with each other.

```bash
docker network ls

docker network inspect <network_name>

docker network create <network_name>

docker network rm <network_name>
```

Docker networks let containers connect securely and conveniently, especially when services need to talk to one another.

---

## Docker System
These commands provide system-level information and help free up space by removing unused Docker resources.

```bash
docker system df

docker system prune

docker system prune -a
```

`docker system df` shows disk usage by Docker objects, while prune commands remove unused containers, images, and networks to reclaim space.

---

## WSL Commands
These commands help you check and manage the Windows Subsystem for Linux environment that is commonly used with Docker Desktop on Windows.

```bash
wsl --status

wsl -l -v

wsl

wsl --shutdown
```

These commands help verify WSL status, list installed distributions, start a Linux shell, and shut down the WSL environment cleanly.