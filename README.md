# Nodejs Redis Pub/Sub ![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

## Project Structure

The project consists of two services:

- Publisher Service: Publishes messages to designated channels in Redis.
- Subscriber Service: Subscribes to specific channels and receives messages published to them.


## Getting Started (Build and Run):

```bash
# Create .env by .env.template
cp server-pub/.env.template server-pub/.env && cp server-sub/.env.template server-sub/.env

# Start containers
docker-compose up --build

# Stop containers
docker-compose down
```



# Endpoints

| Service | Method | Endpoint | body | Description
|:--------|:--------|:--------|:--------| :--------|
|`Service pub` | POST |http://localhost:3001/messages | {"message": "Hello world"} | Create new resource
|`Service sub` | GET | http://localhost:3002/messages |  | Get all resources



# Interacting with Redis (Optional)

Access the redis container in the terminal:
```bash
docker exec -it redis bash
```

To listen to messages in real time use:
```bash
redis-cli subscribe orders  # Replace with the desired channel name
```


Publish a message to a channel:
```bash
redis-cli publish orders "pepperoni pizza"
```