# Node.js Server Hang on Long Request

This repository demonstrates a common issue in Node.js servers: hanging on long-running requests.  The example simulates a long-running operation that blocks the event loop, rendering the server unresponsive to other requests.

The `server.js` file contains the buggy code, and `serverSolution.js` provides a corrected version using asynchronous operations to prevent blocking.

## Bug

The server in `server.js` uses a `while` loop to simulate a 5-second delay. During this time, the event loop is blocked, causing the server to become unresponsive to any further requests. This is a classic example of how synchronous, long-running operations can negatively impact the performance and stability of Node.js applications.

## Solution

The solution in `serverSolution.js` demonstrates the use of `setTimeout` and promises or async/await to handle long-running operations asynchronously.  This prevents blocking the event loop and allows the server to remain responsive even during lengthy tasks.