## Redis Demo

### Spin Up Redis with docker instance

```bash
docker compose up -d # -d for detached mode
```

### Enter into redis container

```bash
docker exec -it redis-db bash # redis-db is the container name provided
```

### Stop the redis container

```bash
docker compose down
```

### Pub/Sub

Pub/Sub is handled by channels. Channels are purposedly same as Kafka Topics, but they are different in architecture and features. A publisher publishes messages into a channel and they do not bother where the message will go. The Subscribers subscribes the channel and the channel pushes the messages to the active subscribers. Message can be lost if any subscriber disconnects before receiving a message.

```bash
# Create a channel just by subscribing into a channel
subscribe <channel_name>

# Publish messages to the channel
publish <channel_name> "<message>"
```
