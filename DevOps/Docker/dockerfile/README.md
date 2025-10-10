A Dockerfile is a plain text file that contains a set of instructions to build a Docker image.

⚙️ Basic Dockerfile Instructions

1. FROM
Defines the base image for your new image.
Every Dockerfile must start with a FROM instruction.

Syntax:
```bash    
FROM <image>[:<tag>] [AS <name>]
```
Example:
```bash
FROM ubuntu:22.04
FROM node:20
FROM python:3.11-slim AS builder
```
AS builder is used for multi-stage builds.

You can chain multiple FROM instructions in one Dockerfile (each creates a new build stage).


2. LABEL
Adds metadata to an image — like version, author, description.
Syntax:

```bash
LABEL key="value"
```
Example:

```bash
LABEL maintainer="anuj@example.com"
LABEL version="1.0" description="Node.js Web App"
```

3. RUN
Executes commands inside the image at build time.
Syntax:

```bash
RUN <command>
RUN ["executable", "param1", "param2"]
```
Example:

```bash
RUN apt-get update && apt-get install -y nginx
RUN npm install
```
Combine commands using && to reduce image layers:

```bash
RUN apt-get update && apt-get install -y curl vim && rm -rf /var/lib/apt/lists/*
```

4. CMD
Specifies the default command to run when a container starts.
Syntax:

```bash
CMD ["executable", "param1", "param2"]   # exec form (recommended)
CMD command param1 param2                # shell form
```
Example:

```bash
CMD ["node", "app.js"]
```

Only one CMD is allowed; if multiple, the last one wins.

You can override CMD at runtime:

docker run myapp echo "Hello"

5. ENTRYPOINT
Sets the main executable of the container.
It is not overridden by default when you pass arguments.

Syntax:

```bash
ENTRYPOINT ["executable", "param1", "param2"]
```
Example:

```bash
ENTRYPOINT ["python", "app.py"]
```

📝 CMD vs ENTRYPOINT:

Command	Overridable	Purpose
CMD	✅ Yes	Default command
ENTRYPOINT	🚫 No	Fixed main process

Example combining both:

```bash
ENTRYPOINT ["ping"]
CMD ["google.com"]
```
Result: Runs ping google.com by default.

6. WORKDIR

Sets the working directory inside the container.
If the directory doesn’t exist, Docker creates it.
Example:

```bash
WORKDIR /usr/src/app
COPY . .
RUN npm install
```

7. COPY
Copies files/folders from your local system into the image.
Syntax:

```bash
COPY <src> <dest>
```

Example:

```bash
COPY . /usr/src/app
COPY package.json /usr/src/app/
```
Use .dockerignore to skip unnecessary files (like node_modules).

8. ADD

Similar to COPY, but with extra features:
Can extract tar files
Can copy files from a URL

Example:

```bash
ADD app.tar.gz /usr/src/app/
ADD https://example.com/file.txt /usr/src/app/
```

🧠 Best Practice:
Use COPY unless you specifically need ADD’s extra features.

9. EXPOSE
Documents the port your container listens on.

Syntax:

```bash
EXPOSE <port> [<port>/<protocol>]
```

Example:

```bash
EXPOSE 80
EXPOSE 3000/tcp
```

10. ENV
Sets environment variables inside the image.
Syntax:
ENV <key> <value>
Example:

```bash
ENV NODE_ENV=production
ENV PORT=3000
```

11. ARG
Defines build-time variables (used only during build).
ARG <name>[=<default_value>]
Example:

```bash
ARG APP_VERSION=1.0
RUN echo "Version: $APP_VERSION"
```
🧠 Difference:

```bash
ARG = build-time
ENV = runtime (inside container)
```

12. VOLUME
Creates a mount point for persistent or shared data.
Example:

```bash
VOLUME ["/data"]
```
or

```bash
VOLUME /var/lib/mysql
```
13. USER
Sets which user runs the commands inside the container.
Example:

```bash
RUN useradd -m anuj
USER anuj
```

🧠 Best practice:
Always use a non-root user for better security.

14. HEALTHCHECK
Tells Docker how to test if the container is healthy.
Example:
```bash
HEALTHCHECK --interval=30s --timeout=5s --retries=3 \
```
CMD curl -f http://localhost:3000/health || exit 1

🧠 Docker marks the container as:
healthy
unhealthy
starting

15. SHELL
Changes the default shell used for RUN commands.
Example:

```bash
SHELL ["/bin/bash", "-c"]
```

16. ONBUILD
Adds a trigger instruction that runs when another image uses your image as a base.
Example:

```bash
ONBUILD COPY . /app
ONBUILD RUN npm install
```

🧠 Used in base images to automate actions for child images.
17. COPY --from=
Used in multi-stage builds to copy files from another build stage.
Example:
```bash
FROM node:20 AS builder
WORKDIR /app
COPY . .
RUN npm install && npm run build
FROM node:20-slim
WORKDIR /app
COPY --from=builder /app/dist ./dist
CMD ["node", "dist/app.js"]
```

🧠 Multi-stage builds make images smaller and faster.
19. MAINTAINER (Deprecated)
Older way to define author:
MAINTAINER Anuj <anuj@example.com>
➡️ Use LABEL maintainer="anuj@example.com" instead.
