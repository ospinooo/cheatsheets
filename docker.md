
# Docker





## Dockerfile
### Instructions

> Instructions to create the steps in the dockerfile
> 
- **FROM** — specifies the base (parent) image.
- **LABEL** —provides metadata. Good place to include maintainer info.
- **ENV** — sets a persistent environment variable.
- **RUN** —runs a command and creates an image layer. Used to install packages into containers.
- **COPY** — copies files and directories to the container.
- **ADD** — copies files and directories to the container. Can upack local .tar files.
- **CMD** — provides a command and arguments for an executing container. Parameters can be overridden. There - can be **only** one CMD.
- **WORKDIR** — sets the working directory for the instructions that follow.
- **ARG** — defines a variable to pass to Docker at build-time.
- **ENTRYPOINT** — provides command and arguments for an executing container. Arguments persist.
- **EXPOSE** — exposes a port.
- **VOLUME** — creates a directory mount point to access and store persistent data.

## Data persistence

> Persist application data when the container dies.

- Volumes: host file system managed by Docker
- Bind mounts: Anywhere in the system
- tmpfs mounts

```sh
docker volume create <volume_name> # create a volume
docker volume ls # See all volumes
```

Mapped the host folder to a volume that will be mounted inside our container
```sh
docker run -v <host_folder>:<volume_name> <container_image> # Mouniting a data volume to a container
```

Mapped 