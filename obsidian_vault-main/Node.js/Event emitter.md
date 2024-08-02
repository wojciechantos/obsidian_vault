[Documentation](https://nodejs.org/api/events.html)
[Module](https://github.com/nodejs/nodejs.dev/blob/aa4239e87a5adc992fdb709c20aebb5f6da77f86/content/learn/node-js-modules/node-module-events.en.md)

Just like the browser does, Node.js also provides a way of handling various events with help of `events module`.

This module offers the `EventEmitter` class. To initialize it:

```js
import EventEmitter from 'node:events';

const eventEmitter = new EventEmitter();
```

The object exposes (among many others) the `on` and `emit` methods.

- `emit` is used to trigger an event
- `on` is used to add a callback function that's going to be executed when the event is triggered

```js
import EventEmitter from 'node:events';  
  
const eventEmitter = new EventEmitter();  
  
eventEmitter.on('start', () => {  
  console.log('started');  
});  
  
eventEmitter.emit('start');
```

Additional arguments can be passed to `emit()` to be passed to the event handler:

```js
eventEmitter.on('start', (start, end) => { 
	console.log(`started from ${start} to ${end}`);
});
	
eventEmitter.emit('start', 1, 100);
```

The EventEmitter object also exposes several other methods to interact with events, like:
- `once()`: add a one-time listener
- `removeListener()` / `off()`: remove an event listener from an event
- `removeAllListeners()`: remove all listeners for an event

