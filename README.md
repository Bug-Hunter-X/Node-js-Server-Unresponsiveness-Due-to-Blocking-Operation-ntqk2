# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation within a request handler blocks the event loop, causing the server to become unresponsive.  The `server.js` file contains the buggy code, and `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The original `server.js` uses a `while` loop to simulate a long-running task that takes 5 seconds.  During this time, the event loop is blocked, preventing the server from accepting and processing new requests.  This leads to unresponsiveness and poor performance.

## Solution

The `serverSolution.js` file demonstrates how to fix this issue by using asynchronous operations. Instead of a blocking `while` loop, we use `setTimeout` to simulate an asynchronous task, which releases the event loop and allows for concurrent processing of requests.

This example is a simplified illustration.  In real-world scenarios, long-running operations might involve database interactions, file I/O, or network requests.  The solution always involves switching to asynchronous or non-blocking approaches.