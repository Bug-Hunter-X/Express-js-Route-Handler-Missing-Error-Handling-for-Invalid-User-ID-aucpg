# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input.  Specifically, the provided code attempts to parse a user ID from the request parameters as an integer without validating its format.  This can lead to unexpected behavior or application crashes if the ID is not a valid integer.

## Bug
The `bug.js` file contains the flawed code.  It lacks checks to ensure `req.params.id` is a valid number before attempting to parse it with `parseInt()`.  If a non-numeric value is provided, `parseInt()` will return `NaN`, leading to a failure in finding the user.

## Solution
The `bugSolution.js` file provides a corrected version. This version includes input validation to ensure the user ID is a valid number before performing the lookup. This prevents crashes and provides a more robust and user-friendly experience.

## How to reproduce
1. Clone the repository.
2. Run `npm install express` to install the necessary dependencies.
3. Run `node bug.js` and send a request to `/users/abc` (or similar).
4. Observe the error. Repeat with `node bugSolution.js` to see the improved error handling.