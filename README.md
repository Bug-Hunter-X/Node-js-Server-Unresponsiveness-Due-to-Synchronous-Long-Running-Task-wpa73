# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js servers: unresponsiveness caused by long-running synchronous operations within the request handler.  When a request triggers a lengthy process that blocks the event loop, the server cannot accept or process any further requests.

## Problem

The `bug.js` file contains a simple HTTP server. However, the request handler includes a `while` loop that keeps the CPU busy for 5 seconds. During this time, the server is completely unresponsive to new incoming requests.

## Solution

The `bugSolution.js` file presents a solution by refactoring the code to use asynchronous operations.  This allows the event loop to remain active and process other requests concurrently, preventing the server from becoming unresponsive.