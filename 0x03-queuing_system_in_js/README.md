# Queuing System in JS

This project involves creating a queuing system in JavaScript using Redis, Node.js, and Kue. The goal is to gain a comprehensive understanding of setting up a Redis server, performing basic and advanced Redis operations, handling async operations, and integrating Redis with a Node.js application to create and process jobs in a queue.

## Learning Objectives

By the end of this project, you will be able to:
- Run a Redis server on your machine.
- Perform basic operations with the Redis client.
- Use a Redis client with Node.js for basic operations.
- Store and retrieve hash values in Redis.
- Handle asynchronous operations with Redis.
- Use Kue as a queue system.
- Build a basic Express app interacting with a Redis server.
- Build an Express app that interacts with both a Redis server and a queue.

## Requirements

- Code will be compiled/interpreted on Ubuntu 18.04, Node 12.x, and Redis 5.0.7.
- All files should end with a new line.
- A `README.md` file at the root of the project is mandatory.
- Code should use the `.js` extension.

## Tasks Overview

### 0. Install a Redis Instance
- Download and compile the latest stable Redis version.
- Start Redis in the background.
- Use the Redis client to set and get a key-value pair.
- Copy `dump.rdb` to the root of the project.

### 1. Node Redis Client
- Install `node_redis` using npm.
- Create a script `0-redis_client.js` to connect to the Redis server.
- Log connection status to the console.

### 2. Node Redis Client and Basic Operations
- Create `1-redis_op.js` to perform basic Redis operations.
- Add functions to set a new key-value pair and display the value of a key.

### 3. Node Redis Client and Async Operations
- Create `2-redis_op_async.js` to handle Redis operations asynchronously using `promisify`.
- Modify `displaySchoolValue` function to use ES6 async/await.

### 4. Node Redis Client and Advanced Operations
- Create `4-redis_advanced_op.js` to store and retrieve hash values in Redis.
- Use `hset` to create a hash and `hgetall` to display it.

### 5. Node Redis Client Publisher and Subscriber
- Create `5-subscriber.js` to subscribe to a Redis channel and handle messages.
- Create `5-publisher.js` to publish messages to the Redis channel.

### 6. Create the Job Creator
- Create `6-job_creator.js` to create a queue and add jobs to it using Kue.
- Log job creation status to the console.

### 7. Create the Job Processor
- Create `6-job_processor.js` to process jobs from the queue.
- Define a function to handle job processing and log notifications.

## Repository Structure
```
.
├── 0-redis_client.js
├── 1-redis_op.js
├── 2-redis_op_async.js
├── 4-redis_advanced_op.js
├── 5-subscriber.js
├── 5-publisher.js
├── 6-job_creator.js
├── 6-job_processor.js
├── dump.rdb
└── README.md
```

## Setup and Usage

### Installing Redis
1. Download and compile Redis:
   ```bash
   wget http://download.redis.io/releases/redis-6.0.10.tar.gz
   tar xzf redis-6.0.10.tar.gz
   cd redis-6.0.10
   make
   ```

2. Start Redis server:
   ```bash
   src/redis-server &
   ```

3. Verify Redis server is running:
   ```bash
   src/redis-cli ping
   ```

### Running Node.js Scripts
1. Install dependencies:
   ```bash
   npm install
   ```

2. Run scripts using npm:
   ```bash
   npm run dev <script_name.js>
   ```

## Additional Resources
- [Redis Quick Start](https://redis.io/download)
- [Redis Client Interface](https://redis.io/topics/clients)
- [Redis Client for Node.js](https://github.com/redis/node-redis)
- [Kue Documentation](https://github.com/Automattic/kue)

This README provides an overview and guidance for the Queuing System in JS project. Follow the instructions for each task to build and understand a Redis-based queuing system.
