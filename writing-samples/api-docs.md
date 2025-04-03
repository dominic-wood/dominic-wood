# 🧪 Mock API Documentation – Task Manager API

**Version:** 1.0  
**Base URL:** `https://api.taskmanager.dev/v1`  
**Authentication:** Bearer Token (JWT) required for all endpoints except `/auth/register` and `/auth/login`

## 📚 Table of Contents

- [Authentication](#authentication)
  - [POST /auth/register](#post-authregister)
  - [POST /auth/login](#post-authlogin)
- [Tasks](#tasks)
  - [GET /tasks](#get-tasks)
  - [POST /tasks](#post-tasks)
  - [GET /tasks/{id}](#get-tasksid)
  - [PUT /tasks/{id}](#put-tasksid)
  - [DELETE /tasks/{id}](#delete-tasksid)
- [Error Handling](#error-handling)

<a id="authentication"></a>
## 🔐 Authentication

### POST `/auth/register`  
Register a new user account.

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "SecurePass123"
}
```

**Response:**
```json
{
  "message": "User registered successfully."
}
```



### POST `/auth/login`  
Log in and retrieve a JWT token.

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "SecurePass123"
}
```

**Response:**
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

<a id="tasks"></a>
## ✅ Tasks

> All task-related routes require a valid Bearer token in the `Authorization` header.

### GET `/tasks`  
Retrieve a list of tasks for the authenticated user.

**Response:**
```json
[
  {
    "id": 1,
    "title": "Write API docs",
    "completed": false,
    "due_date": "2025-04-10T12:00:00Z"
  },
  {
    "id": 2,
    "title": "Review pull requests",
    "completed": true,
    "due_date": null
  }
]
```

### POST `/tasks`  
Create a new task.

**Request Body:**
```json
{
  "title": "Fix login bug",
  "due_date": "2025-04-15T09:00:00Z"
}
```

**Response:**
```json
{
  "id": 3,
  "title": "Fix login bug",
  "completed": false,
  "due_date": "2025-04-15T09:00:00Z"
}
```

### GET `/tasks/{id}`  
Get details of a specific task.

**Response:**
```json
{
  "id": 3,
  "title": "Fix login bug",
  "completed": false,
  "due_date": "2025-04-15T09:00:00Z"
}
```

### PUT `/tasks/{id}`  
Update an existing task.

**Request Body:**
```json
{
  "title": "Fix login bug (urgent)",
  "completed": true
}
```

**Response:**
```json
{
  "id": 3,
  "title": "Fix login bug (urgent)",
  "completed": true,
  "due_date": "2025-04-15T09:00:00Z"
}
```

### DELETE `/tasks/{id}`  
Delete a task by ID.

**Response:**
```json
{
  "message": "Task deleted successfully."
}
```
<a id="error-handling"></a>
## 🚫 Error Handling

All error responses follow this format:

```json
{
  "error": "Error message goes here."
}
```

**Common Status Codes:**

| Status Code | Meaning                      |
|-------------|------------------------------|
| 200 OK      | Request succeeded             |
| 201 Created | Resource created successfully |
| 400 Bad Request | Invalid input or parameters |
| 401 Unauthorized | Missing or invalid token    |
| 404 Not Found | Resource not found           |

<a href="#top" id="return-to-top">
  ⬆
</a>

<style>
#return-to-top {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background: #007acc;
  color: white;
  padding: 8px 12px;
  text-decoration: none;
  border-radius: 6px;
  font-weight: bold;
  box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}
#return-to-top:hover {
  background: #005fa3;
}
</style>