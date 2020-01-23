# Docker exec

## Description

Run a command in a running container

## Usage

```text
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

## Options

| Name, shorthand | Description |  |  |
| :--- | :--- | :--- | :--- |
| --detach , -d | Detached mode: run command in the background |  |  |
| --detach-keys | Override the key sequence for detaching a container |  |  |
| --env , -e | API 1.25+ Set environment variables |  |  |
| --interactive , -i | Keep STDIN open even if not attached |  |  |
| --privileged | Give extended privileges to the command |  |  |
| --tty , -t | Allocate a pseudo-TTY |  |  |
| --user , -u | Username or UID \(format: &lt;name | uid&gt;\[:&lt;group | gid&gt;\]\) |
| --workdir , -w | API 1.35+ Working directory inside the container |  |  |

## Examples

### Execute an interactive bash shell on the container.

```text
docker exec -it {container_name} bash
```

## References

1. [Official document: docker exec](https://docs.docker.com/engine/reference/commandline/exec/)

