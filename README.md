# Docker Commands Cheat Sheet

A collection of useful Docker commands for managing containers, networks, images, and volumes.

## Container Management

### Display Resource Usage
```bash
docker container stats
```

### Inspect Container
```bash
docker container inspect <container_id>
```

### Show Container's IP Address
```bash
docker container inspect -f '{{.NetworkSettings.IPAddress}}' <container_id>
```

### Run Container
```bash
docker run <options> <image>
```
#### Options:
- `-it` Interactive terminal
- `-d` Detached mode
- `-p <host_port>:<container_port>` Port mapping
- `--rm` Automatically remove container when it exits
- `--name <container_name>` Assign a name to the container
- `-v <container_folder>` Bind mount a volume from the host
- `-v "<volume_name>:<container_folder>"` Bind mount a named volume
- `-v "<host_path>:<container_folder>:ro"` Read-only bind mount
- `--env <env_var_name>=<env_var_value>` Set environment variable
- `--env-file ./.env` Load environment variables from file
- `--build-arg <arg_name>=<arg_value>` Set build-time variables
- `--network <network_name>` Connect container to network

### Attach to Container
```bash
docker attach <container_name>
```

### List All Containers
```bash
docker ps -a
```

### Stop Container
```bash
docker stop <container_name>
```

### Start Container with Interactive Terminal
```bash
docker start -a -i <container_name>
```

### View Container Logs
```bash
docker logs -f <container_name>
```

## Image Management

### Build Image
```bash
docker build -t <repository_name>:<tag> .
```

### Show Image History
```bash
docker history <pulled_image_name>
```

### List All Images
```bash
docker images
```

### Delete Images
```bash
docker image prune -a # Delete all images
docker image prune # Delete untagged images
```

### Inspect Image
```bash
docker image inspect <image_id>
```

### Push Image to Registry
```bash
docker push <image_name>
```

### Pull Image from Registry
```bash
docker pull <image_name>
```

### Tag Image
```bash
docker tag <source_image> <target_image>
```

## Network Management

### List Networks
```bash
docker network ls
```

### Create Network
```bash
docker network create <network_name>
```

### Connect Container to Network
```bash
docker network connect <network_name> <container_name>
```

### Disconnect Container from Network
```bash
docker network disconnect <network_name> <container_name>
```

## Volume Management

### List Volumes
```bash
docker volume ls
```

### Create Volume
```bash
docker volume create <volume_name>
```

### Prune Volumes
```bash
docker volume prune
```

### Inspect Volume
```bash
docker volume inspect <volume_name>
```

### Remove Volume
```bash
docker volume rm <volume_name>
```

## Docker Compose

### Start Containers Defined in Compose File
```bash
docker-compose up
```

### Force Rebuild Images and Start Containers
```bash
docker-compose up --build
```

### Stop Containers
```bash
docker-compose down
```

### Stop Containers and Delete Volumes
```bash
docker-compose down -v
```

### Build Images Defined in Compose File
```bash
docker-compose build
```

### Run a Single Container from Compose File
```bash
docker-compose run --rm <container_name>
```

## Authentication

### Show Docker Configuration
```bash
cat /root/.docker/config.json
```

### Login to Docker Registry
```bash
docker login
```

### Logout from Docker Registry
```bash
docker logout
```

Feel free to contribute and expand this cheat sheet! 🐳✨