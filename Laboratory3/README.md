# 🖥️ Lab 3 - Working with JSON and External APIs

## 📌 Description
This project demonstrates how to interact with external APIs, manipulate the data in Python, and return the processed information as JSON. It includes creating APIs that call other APIs, filter and format data, and return the results in a structured JSON format.

## 📖 Learning Objectives
- Understanding how to retrieve data from external APIs.
- Manipulating data in Python based on specific parameters.
- Creating new APIs that interact with multiple external APIs.
- Returning structured data in valid JSON format.

## 📝 Code Explanation
The project has multiple API endpoints that interact with external APIs and return data in different formats:
- **GET /posts/**: Fetches a list of posts from an external API, optionally filtered by `postId`.
- **GET /comments/**: Fetches comments related to posts from an external API, optionally filtered by `postId`.
- **GET /formatted_posts/{userID}**: Returns posts specific to a `userID` in a formatted structure.
- **GET /formatted_comment/{postID}**: Returns comments for a specific `postID` in a formatted structure.
- **GET /detailed_post/{userID}**: Retrieves all posts for a specific user and includes the related comments for each post.

### ✅ **Code Breakdown**
- `requests.get()` is used to fetch data from external APIs (`https://jsonplaceholder.typicode.com`).
- `json.loads()` is used to parse the JSON response and convert it to Python data types.
- Each API endpoint retrieves and manipulates the data based on the given parameters.

## 📜 Example Outputs
| Endpoint | Input | Output |
|----------|-------|--------|
| **GET /posts/** | No query parameter | `{ "status": "ok", "result": [{ "id": 1, "title": "Post title", "body": "Post body content" }] }` |
| **GET /comments/** | No query parameter | `{ "status": "ok", "result": [{ "postId": 1, "email": "email@example.com", "body": "Comment text" }] }` |
| **GET /formatted_posts/1** | `userID=1` | `{ "userID": 1, "posts": [{"post_title": "Title", "post_body": "Body"}] }` |
| **GET /formatted_comment/1** | `postID=1` | `{ "post_id": 1, "comments": [{"commenter_email": "email@example.com", "commenter_name": "User", "comment": "Comment text"}] }` |
| **GET /detailed_post/1** | `userID=1` | `{ "userID": 1, "detailed_posts": [{"post_title": "Title", "post_body": "Body", "comments": [{"email": "email@example.com", "name": "User", "comment": "Comment text"}]}] }` |
