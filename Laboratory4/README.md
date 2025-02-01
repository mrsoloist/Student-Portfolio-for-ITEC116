# 🖥️ Lab 4 - Advanced API Implementation with FastAPI

## 📌 Description
This project demonstrates how to implement an advanced API using **FastAPI** with **API key authentication** and **task management**. It features two versions of the API (v1 and v2), where users can create, retrieve, update, and delete tasks. The API is secured by an API key, which is required to access the endpoints. This project showcases how to structure an API with versioning and security mechanisms.

## 📖 Learning Objectives
- Implementing versioned APIs (v1 and v2) in FastAPI.
- Securing APIs with API key authentication.
- Creating a task management system with CRUD operations (Create, Read, Update, Delete).
- Using **dependency injection** to manage API key validation.

## 📝 Code Explanation
This project has multiple API endpoints to manage tasks for two versions (v1 and v2). It includes functionality for creating tasks, fetching specific tasks by ID, updating task details, and deleting tasks. All endpoints are protected by an API key, which is validated via a **dependency function**.

### API Endpoints:
- **GET /apiv1/**: Returns a welcome message for API v1.
- **GET /apiv1/tasks/{task_id}**: Fetches a task by `task_id` from **API v1**.
- **POST /apiv1/tasks/**: Creates a new task in **API v1** with a given `task_title` and `task_desc`.
- **DELETE /apiv1/tasks/{task_id}**: Deletes a task by `task_id` from **API v1**.
- **PATCH /apiv1/tasks/{task_id}**: Updates an existing task in **API v1** with optional fields (`task_title`, `task_desc`, `is_finished`).
- **GET /apiv2/tasks/{task_id}**: Fetches a task by `task_id` from **API v2**.
- **POST /apiv2/tasks/**: Creates a new task in **API v2**.
- **DELETE /apiv2/tasks/{task_id}**: Deletes a task by `task_id` from **API v2**.
- **PATCH /apiv2/tasks/{task_id}**: Updates an existing task in **API v2**.

### ✅ **Code Breakdown**
- `load_dotenv()` is used to load the **API key** from the `.env` file.
- `Depends(verify_api_key)` is used as a dependency to secure the API endpoints by checking the API key from the request headers or query parameters.
- **CRUD Functions**: 
  - `get_task_by_id()`: Retrieves a task by its ID.
  - `create_task()`: Adds a new task to the database.
  - `delete_task()`: Deletes a task from the database.
  - `update_task()`: Updates a task's details.
  
- The **in-memory databases** (`task_db_v1` and `task_db_v2`) store tasks for both API versions.

## 📜 Example Outputs

| Endpoint                          | Input                                    | Output                                                                                              |
|-----------------------------------|------------------------------------------|-----------------------------------------------------------------------------------------------------|
| **GET /apiv1/**                    | None                                     | `{ "message": "Welcome to API v1" }`                                                                |
| **GET /apiv1/tasks/1**             | `task_id=1`                              | `{ "status": "ok", "task": { "task_id": 1, "task_title": "Test 1", "task_desc": "Complete FastAPI basics", "is_finished": false } }` |
| **POST /apiv1/tasks/**             | `task_title="Test 3", task_desc="Learn OAuth"` | `{ "status": "ok", "task": { "task_id": 2, "task_title": "Test 3", "task_desc": "Learn OAuth", "is_finished": false } }` |
| **DELETE /apiv1/tasks/1**          | `task_id=1`                              | `{ "status": "ok", "message": "Task deleted successfully" }`                                         |
| **PATCH /apiv1/tasks/2**           | `task_id=2, task_title="Updated Task", task_desc="Master OAuth"` | `{ "status": "ok", "task": { "task_id": 2, "task_title": "Updated Task", "task_desc": "Master OAut
