# Docker inspect

## Examples

### Inspect volumes attached to a container

```text
docker inspect -f '{{ .Mounts }}' container_id
```

## References

1. [Stack Overflow: How do you list volumes in docker containers?](https://stackoverflow.com/questions/30133664/how-do-you-list-volumes-in-docker-containers)

