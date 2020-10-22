# Node.js

Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google’s V8 JavaScript engine and libuv library.

Node.js is event driven, so everything that happens in node is a reaction to an event. 

## Execution Model 
When we connect to a server, it will create a new thread and any subsequent I/O operations block the execution of the code until the operation is completed. If new requests come while this is happening, it slows down, and in large numbers, may cause the site to go down.

## Advantages
- You can do everything in the same language
- It speaks JSON, which is the most important data exchange format on the web 
- JavaScript is ubiquitous, meaning that switching over to Node development is really easy

## Downsides

- Blocking I/O calls should be avoided
- CPU-intensive operations should be handed off to a worker thread
- Errors should always be handled correctly for fear of crashing the entire process.

## What kind of Apps is Node.js suited for?

Applications that have real-time interaction or collaboration use node.js. Another is for building APIs that handle multiple requests or data streaming.

[Back to Home Page](https://kmangub.github.io/reading-notes-master/)
