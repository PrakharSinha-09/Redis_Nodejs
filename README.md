# Redis Queues Implementation with Node.js (Express Backend)

This project demonstrates how to implement Redis queues using a Node.js backend with Express. The setup includes running Redis on Docker, starting an Express server, and managing worker services.

## Prerequisites

- [Docker](https://www.docker.com/get-started)
- [Node.js](https://nodejs.org/) (version 12 or higher)
- [npm](https://www.npmjs.com/)

## Getting Started

### Step 1: Start Redis with Docker
First, you need to start a Redis instance using Docker. Open your terminal and run the following command:

```bash
docker run --name my-redis -d -p 6379:6379 redis
This command pulls the Redis Docker image (if not already available) and runs it, exposing Redis on port 6379.
```

### Step 2: Set Up the Express Backend
Navigate to the express-backend folder and install the necessary dependencies:

```bash
cd express-backend
npm install
```

After installing the dependencies, start the Express server:
```bash
node dist/index.js
```

### Step 3: Set Up the Worker Service
Navigate to the worker folder and install the dependencies:

```bash
cd ../worker
npm install
```

Start the worker service by running:

```bash
node dist/index.js
```

You can start multiple worker instances by running the above command multiple times in different terminal windows or tabs.


### Step 4: Testing with Postman
Now that your server and workers are running, you can test the setup using Postman or any other API testing tool. Send requests to the Express server, which will manage the queueing and processing of tasks using the worker services.

### Project Structure
express-backend: Contains the Express server implementation.  
worker: Contains the worker service that processes tasks from the Redis queue.