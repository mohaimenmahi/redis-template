## Redis Demo

### Spin Up Redis with docker instance

```bash
docker compose up -d # -d for detached mode
```

### Enter into the redis container

```bash
docker exec -it redis-db bash # redis-db is the container name provided
```

### Start using Redis by redis-cli
```bash
redis-cli
```

### Set some value
```bash
Syntax: SET key value [EX seconds] [PX milliseconds] [NX | XX] [KEEPTTL] [GET]
Examples:
SET mykey "Hello Redis": Sets the key mykey to the string value "Hello Redis".
SET mykey "New Value" EX 60: Sets mykey to "New Value" and sets an expiration time of 60 seconds.
SET anotherkey "Only if not exists" NX: Sets anotherkey only if it does not already exist.
SET existingkey "Update if exists" XX: Sets existingkey only if it already exists.
SET mykey "Updated Value" GET: Sets mykey to "Updated Value" and returns the old value of mykey.
```

### Get values
```bash
Syntax: GET key
Examples:
GET mykey: Retrieves the value of mykey.
If mykey exists and holds a string value, that value is returned.
If mykey does not exist, or if it holds a non-string data type, a special value nil (or equivalent in client libraries) is returned.
```

### Stop the Redis container

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
