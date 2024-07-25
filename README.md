# Distributed Task Scheduler with Real-Time Monitoring

## Description
A distributed task scheduler built with Node.js, Express, MongoDB, and Redis. This system supports task creation, scheduling, execution across multiple nodes, real-time monitoring, and alerting.

## Features
- User authentication and authorization with JWT
- Task creation, scheduling, and management
- Distributed task execution across multiple nodes
- Real-time monitoring and task status updates with Socket.io
- Alerting for task failures or critical events
- Caching with Redis for performance optimization
- Centralized logging and error tracking

## Prerequisites
- Node.js
- MongoDB
- Redis
- Git
- Postman

## Installation
1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/task-scheduler.git
    cd task-scheduler
    ```

2. Install dependencies:
    ```sh
    npm install
    ```

3. Set up environment variables:
    ```sh
    cp .env.example .env
    ```
    Update `.env` with your MongoDB, Redis, and JWT configuration.

4. Start the server:
    ```sh
    npm start
    ```

## API Endpoints

### Authentication
- **POST /api/auth/register**: Register a new user.
    ```json
    {
        "username": "john_doe",
        "email": "john@example.com",
        "password": "securepassword"
    }
    ```

- **POST /api/auth/login**: Log in a user.
    ```json
    {
        "email": "john@example.com",
        "password": "securepassword"
    }
    ```

### Tasks
- **POST /api/tasks**: Create a new task.
    ```json
    {
        "name": "Task Name",
        "schedule": "0 0 * * *",  // Cron expression
        "command": "node task.js"
    }
    ```

- **GET /api/tasks**: Get all tasks.
- **GET /api/tasks/:id**: Get task by ID.
- **PUT /api/tasks/:id**: Update a task.
- **DELETE /api/tasks/:id**: Delete a task.

### Monitoring
- **GET /api/monitoring/tasks**: Get the status of all tasks.
- **GET /api/monitoring/tasks/:id**: Get the status of a specific task.

### Alerts
- **POST /api/alerts**: Create a new alert rule.
    ```json
    {
        "taskId": "task_id",
        "condition": "failed",  // Condition for the alert
        "email": "alert@example.com"
    }
    ```

- **GET /api/alerts**: Get all alert rules.
- **DELETE /api/alerts/:id**: Delete an alert rule.

## Real-Time Features
- **WebSockets**: Implement WebSocket connections for real-time task status updates and alerts.

## Postman Collection
A Postman collection is included in the repository. Import it into Postman to test the API endpoints.

## License
This project is licensed under the MIT License.
