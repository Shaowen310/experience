# Docker run

## Description

Run a command in a new container

## Usage

```text
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

## Examples

### Mount a volume

```text
docker run -v /doesnt/exist:/foo -w /foo -i -t ubuntu bash
```

The `-v` flag mounts the current working directory into the container. The `-w` lets the command being executed inside the current working directory, by changing into the directory to the value provided, i.e. `/foo`.

When the host directory of a bind-mounted volume doesn’t exist, Docker will automatically create this directory on the host for you. In the example above, Docker will create the `/doesnt/exist` folder before starting your container.

## References

1. [Official document: docker run](https://docs.docker.com/engine/reference/commandline/run/)

