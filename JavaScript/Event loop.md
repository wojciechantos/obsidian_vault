Event Loop is an essential component of the JS execution environment which guarantees that although JS is single threaded, the operations can be executed in paralel.

When JS code is being executed, the code is being processed line by line (single-threaded). But what about the operations that need some time like API calls, DOM manipulations, user dependant events, I/O etc.? - Here the event loop comes into play.

Here is how an event loop works (simplified):

1. Call stack executes all the synchronous operations from top to bottom.
2. When call stack stumps upon an asynchronous operation like setTimeout, fetch etc., it sends it to the Web API (provided by a browser) to handle it.
3. When the Web API finishes handling the asynchronous operations, it transfers them in the callback queue.
4. The event loop constantly monitors the call stack and the callback queue. When the call stack is empty, the event loop takes the first callback from the callback queue and transfers it to the call stack to be executed. This process runs until the queue runs out of tasks.  
