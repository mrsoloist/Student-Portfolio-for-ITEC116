# 🖥️ Lab 1 - FastAPI Factorial API

## 📌 Description
This project demonstrates how to use **FastAPI** to create a simple web API that calculates the factorial of a given number.  

## 📖 Learning Objectives
- Understanding the basics of **FastAPI**.
- Creating an API endpoint with a path parameter.
- Implementing a factorial calculation using Python.

## 📝 Code Explanation
The API has a single **GET** endpoint:  
`/factorial/{starting_number}`  
When a user accesses this endpoint with a number (e.g., `/factorial/5`), the API returns the factorial of that number.

### ✅ **Code Breakdown**
- `FastAPI()` initializes the API.
- The `@application.get("/factorial/{starting_number}")` defines the route.
- The function `factorial(starting_number: int)`:
  - Returns `False` if the input is **0**.
  - Uses a `while` loop to calculate the factorial.
  - Returns the computed factorial as a JSON response.

## 📜 Example Outputs
| Input | Output |
|-------|--------|
| `/factorial/5` | `{ "result": 120 }` |
| `/factorial/3` | `{ "result": 6 }` |
| `/factorial/0` | `{ "result": false }` |
