# Unhandled Error in Express.js Route Handler

This repository demonstrates a common error in Express.js applications: missing error handling in route handlers.  Specifically, the `/users/:id` route does not handle cases where the `userId` is invalid or a user with that ID is not found.

The `bug.js` file shows the erroneous code, while `bugSolution.js` provides a corrected version with proper error handling.

## Bug

The original code lacks error handling for scenarios such as:

* **Invalid User ID:** The `userId` might not be a valid integer or might not exist in the database.
* **Database Errors:**  The database query might fail due to various reasons (connection errors, etc.).

These situations lead to unhandled exceptions, causing the server to crash or return a generic 500 error to the client.

## Solution

The corrected code in `bugSolution.js` demonstrates how to handle these errors gracefully:

* It uses `try...catch` blocks to wrap database operations and catch potential errors.
* It returns appropriate HTTP error codes (e.g., 404 Not Found) to the client in case of errors.
* It provides informative error messages to help with debugging.

This approach ensures better resilience and user experience for the application.