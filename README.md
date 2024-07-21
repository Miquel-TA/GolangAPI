Certainly! Here's a concise README using GitHub's markdown format:

```markdown
# Simple Go RESTful API

This is a simple RESTful API written in Go using only the standard library.

## Features

- Retrieve all users
- Retrieve a single user by ID
- Create a new user
- Delete a user by ID

## Setup

Run the API server:

```bash
go run main.go
```

The API server will start on `http://localhost:8000`.

## Endpoints

### Get All Users

- **URL**: `/users`
- **Method**: `GET`
- **Success Response**:
  - **Code**: 200
  - **Content**: 
  ```json
  [{"id":"1","name":"John Doe","email":"john@example.com"}, {...}]
  ```

### Get User by ID

- **URL**: `/users/{id}`
- **Method**: `GET`
- **URL Params**: `id=[string]`
- **Success Response**:
  - **Code**: 200
  - **Content**: 
  ```json
  {"id":"1","name":"John Doe","email":"john@example.com"}
  ```

### Create User

- **URL**: `/users`
- **Method**: `POST`
- **Data Params**: JSON body 
  ```json
  {"id":"3","name":"New User","email":"newuser@example.com"}
  ```
- **Success Response**:
  - **Code**: 200
  - **Content**: 
  ```json
  {"id":"3","name":"New User","email":"newuser@example.com"}
  ```

### Delete User

- **URL**: `/users/{id}`
- **Method**: `DELETE`
- **URL Params**: `id=[string]`
- **Success Response**:
  - **Code**: 200
  - **Content**: `[]` (remaining users)

## Example Requests

```bash
# Get all users
curl -X GET http://localhost:8000/users

# Get user by ID
curl -X GET http://localhost:8000/users/1

# Create a new user
curl -X POST http://localhost:8000/users -d '{"id":"3","name":"New User","email":"newuser@example.com"}' -H "Content-Type: application/json"

# Delete an user
curl -X DELETE http://localhost:8000/users/1
```
