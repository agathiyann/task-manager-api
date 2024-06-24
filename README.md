
# Task Manager API

This is the backend API for the Task Manager application. It is built using Node.js, Express, and MongoDB. The API provides endpoints to create, read, update, and delete tasks.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Configuration](#configuration)
- [Error Handling](#error-handling)
- [License](#license)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/agathiyann/task-manager-api.git
   cd task-manager-api
   ```

2. Install the dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory with the following environment variables:
   ```env
   PORT=5001
   MONGODB_URI=mongodb+srv://agathiyan:sikkiesu@taskmanager.epeu1mf.mongodb.net/?retryWrites=true&w=majority&appName=taskmanager
   ```

## Usage

1. Start the server:
   ```bash
   npm start
   ```

2. The server will run on `http://localhost:5001` by default.

## API Endpoints

### Tasks

- **Get all tasks**
  ```http
  GET /tasks
  ```
  Response:
  ```json
  [
    {
      "_id": "60d5ec49fc13ae509b000001",
      "title": "Task 1",
      "description": "Description 1",
      "dueDate": "2024-06-24T00:00:00.000Z"
    },
    ...
  ]
  ```

- **Get a task by ID**
  ```http
  GET /tasks/:id
  ```
  Response:
  ```json
  {
    "_id": "60d5ec49fc13ae509b000001",
    "title": "Task 1",
    "description": "Description 1",
    "dueDate": "2024-06-24T00:00:00.000Z"
  }
  ```

- **Create a new task**
  ```http
  POST /tasks
  ```
  Request body:
  ```json
  {
    "title": "Task 1",
    "description": "Description 1",
    "dueDate": "2024-06-24"
  }
  ```
  Response:
  ```json
  {
    "_id": "60d5ec49fc13ae509b000001",
    "title": "Task 1",
    "description": "Description 1",
    "dueDate": "2024-06-24T00:00:00.000Z"
  }
  ```

- **Update a task**
  ```http
  PUT /tasks/:id
  ```
  Request body:
  ```json
  {
    "title": "Updated Task 1",
    "description": "Updated Description 1",
    "dueDate": "2024-06-25"
  }
  ```
  Response:
  ```json
  {
    "_id": "60d5ec49fc13ae509b000001",
    "title": "Updated Task 1",
    "description": "Updated Description 1",
    "dueDate": "2024-06-25T00:00:00.000Z"
  }
  ```

- **Delete a task**
  ```http
  DELETE /tasks/:id
  ```
  Response:
  ```json
  {
    "message": "Task deleted successfully"
  }
  ```

## Configuration

The application uses environment variables for configuration. Create a `.env` file in the root directory with the following variables:

- `PORT`: The port number on which the server will run.
- `MONGODB_URI`: The connection string for the MongoDB database.

## Error Handling

The API uses standard HTTP status codes to indicate the success or failure of an API request. In case of an error, the response will include an error message.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
```

