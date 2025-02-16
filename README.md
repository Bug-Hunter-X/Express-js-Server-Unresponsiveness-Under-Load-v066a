# Express.js Server Unresponsiveness Under Load

This repository demonstrates a common issue in Express.js applications where the server becomes unresponsive or slow when handling requests that require significant processing time.  The bug lies in the lack of proper mechanisms to handle long-running tasks without blocking the event loop.  The solution showcases how to address this by employing asynchronous techniques like promises or async/await.

## Bug

The `server.js` file contains an Express.js server that simulates a 5-second delay for the root route. This delay can cause the server to appear unresponsive, especially if multiple requests arrive concurrently.

## Solution

The `server-fixed.js` file demonstrates how to mitigate this issue by using `async/await` to prevent the event loop from being blocked.  This allows the server to handle other requests concurrently even while processing the long-running task.