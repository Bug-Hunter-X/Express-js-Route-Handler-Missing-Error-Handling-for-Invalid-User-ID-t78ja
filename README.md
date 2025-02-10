# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input. Specifically, the code attempts to parse a user ID from a route parameter as an integer without checking if it's a valid number. This can lead to unexpected behavior or crashes.

## Bug

The `bug.js` file contains the buggy code.  The route handler for `/users/:id` attempts to find a user by ID.  However, if the `id` parameter is not a valid integer, `parseInt(userId)` will return `NaN`, causing the `find` method to fail silently or potentially throw an error, depending on the structure of `users`. 

## Solution

The `bugSolution.js` file provides a corrected version. The solution adds input validation to ensure the `userId` is a valid number before attempting to find the user.  It also includes more robust error handling to return appropriate HTTP status codes.