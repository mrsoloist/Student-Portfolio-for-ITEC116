# 🖥️ Lab 2 - FastAPI User Management API

## 📌 Description
This project demonstrates how to use **FastAPI** to create a simple web API that allows you to manage users in a database. It supports **GET**, **POST**, **DELETE**, and **PUT** operations.

## 📖 Learning Objectives
- Understanding how to handle HTTP actions in **FastAPI**.
- Using query parameters, path parameters, and request bodies.
- Managing in-memory data with FastAPI.

## 📝 Code Explanation
The API has four main endpoints:  
- **GET /users**: Retrieves all users or a specific user by `user_id`.
- **POST /users**: Creates a new user.
- **DELETE /users/{user_id}**: Deletes a user by `user_id`.
- **PUT /users/{user_id}**: Updates a user's details.

### ✅ **Code Breakdown**
- `FastAPI()` initializes the API.
- `@app.get("/users")` defines the route for retrieving users.
- The `read_users(user_id: Optional[int] = None)` function:
  - Returns all users if no `user_id` is provided.
  - Returns the user with the matching `user_id` if provided.
- `@app.post("/users")` handles creating a new user.
- `@app.delete("/users/{user_id}")` deletes a user by `user_id`.
- `@app.put("/users/{user_id}")` updates a user's details.

## 📜 Example Outputs
| Endpoint | Input | Output |
|----------|-------|--------|
| **GET /users** | No query parameter | `{ "status": "ok", "result": [{"user_id": 1, "name": "John Doe"}] }` |
| **GET /users?user_id=1** | `user_id=1` | `{ "status": "ok", "result": {"user_id": 1, "name": "John Doe"} }` |
| **POST /users** | `{ "user_id": 4, "name": "New User" }` | `{ "status": "ok" }` |
| **DELETE /users/1** | `user_id=1` | `{ "status": "ok", "removed_data": {"user_id": 1, "name": "John Doe"} }` |
| **PUT /users/2** | `{ "name": "Updated Name" }` | `{ "status": "ok", "updated_data": {"user_id": 2, "name": "Updated Name"} }` |
