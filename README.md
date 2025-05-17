## Redis Demo

### Spin Up Redis with docker instance

```bash
docker compose up -d (-d for detached mode)
```

### Enter into redis container

```bash
docker exec -it redis-db bash # redis-db is the container name provided
```

### Stop the redis container

```bash
docker compose down
```
