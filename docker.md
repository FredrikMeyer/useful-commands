# Docker

## Prune

Docker tends to eat disk space. Every time Docker is run, a new container is made, and they are not automatically deleted.

```
docker system prune --volumes
```

See [here](https://docs.docker.com/config/pruning/#prune-everything).
