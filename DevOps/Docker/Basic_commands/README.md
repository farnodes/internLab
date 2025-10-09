🐳 1. Check Docker Version & Info

```bash
docker --version
docker version
docker info
```
🔹 docker --version → Shows Docker version.
🔹 docker info → Displays system-wide Docker info (containers, images, storage driver, etc.).


📦 2. Image Commands

🔹 List all images
```bash
docker images
```

🔹 Pull image from Docker Hub
```bash
docker pull ubuntu
```
🔹 Remove an image

```bash
docker rmi ubuntu
```
🔹 Build an image from Dockerfile

```bash
docker build -t myapp:1.0 .
```

(-t → tag the image with name and version)

🚀 3. Container Commands
🔹 Run a container

```bash
docker run ubuntu
```

🔹 Run interactively (with terminal access)
```bash
docker run -it ubuntu /bin/bash
```

🔹 Run in background (detached mode)

```bash
docker run -d nginx
```
🔹 List running containers

```bash
docker ps
```
🔹 List all containers (including stopped)

```bash
docker ps -a
```

🔹 Stop a running container
```bash
docker stop container_id
```
🔹 Start a stopped container

```bash
docker start container_id
```
🔹 Restart a container

```bash
docker restart container_id
```
🔹 Remove a container

```bash
docker rm container_id
```
🔹 Remove all stopped containers

```bash
docker container prune
```

📁 4. File & Logs

🔹 View container logs
```bash
docker logs container_id
```

🔹 Copy files between host and container

```bash
docker cp myfile.txt container_id:/tmp
```
Example:]

```bash
docker cp container_id:/tmp/myfile.txt .
```

⚙️ 5. Exec (Run Command inside Running Container)

```bash
docker exec -it container_id /bin/bash
```

🧹 6. Cleanup Commands
🔹 Remove all containers and images

```bash
docker system prune -a
```
(Removes stopped containers, unused images, and networks)
