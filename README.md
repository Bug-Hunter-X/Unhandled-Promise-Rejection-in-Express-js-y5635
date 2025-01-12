# Unhandled Promise Rejection in Express.js

This example demonstrates a common error in Express.js applications: neglecting to handle potential errors within asynchronous operations.  The `someAsyncOperation` function simulates an operation that might fail.  Without proper error handling, a rejected promise can lead to an uncaught exception and application instability.

## Bug

The `bug.js` file shows an Express.js application with an asynchronous operation (`someAsyncOperation`).  The `.catch()` block is present but empty, meaning errors are not handled correctly.

## Solution

The `bugSolution.js` file demonstrates the correct way to handle errors in this scenario.  The `.catch()` block now includes error logging and sends an appropriate error response to the client.

## How to reproduce

1.  Clone this repository.
2.  Run `npm install` to install Express.js.
3.  Run `node bug.js` and observe that no error response is sent to the client. The server keeps running but it might unexpectedly fail. 
4. Run `node bugSolution.js` and observe that when the error occurs, a 500 status code and error message are returned to the client.