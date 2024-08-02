[Documentation](https://github.com/nodejs/nodejs.dev/blob/aa4239e87a5adc992fdb709c20aebb5f6da77f86/content/learn/node-js-modules/node-module-fs.en.md)

The `fs` module provides a lot of very useful functionality to access and interact with the file system.

There is no need to install it. Being part of the Node.js core, it can be used by simply requiring it:

```js
const fs = require('fs');
```

One peculiar thing about the `fs` module is that all the methods are asynchronous by default, but they can also work synchronously by appending `Sync`.

For example:

- `fs.rename()`
- `fs.renameSync()`
- `fs.write()`
- `fs.writeSync()`

Example, the `fs.rename()` method. The asynchronous API is used with a callback:

```js
const fs = require('fs');

fs.rename('before.json', 'after.json', err => {
  if (err) {
    return console.error(err);
  }

  // done
});
```
A synchronous API can be used like this, with a try/catch block to handle errors:
```js
const fs = require('fs');

try {
  fs.renameSync('before.json', 'after.json');
  // done
} catch (err) {
  console.error(err);
}
```

The key difference here is that the execution of the script will block in the second example, until the file operation succeeded.

### Appending content to an existing file

```js
import fs from 'node:fs';  
  
const content = '\nSome content appended!';  
  
fs.appendFile('append.txt', content, (err) => {  
  if (err) {  
   console.error(err);  
  } else {  
   console.log('Successfully appended content!');  
  }  
});

// with promise

import fs from 'node:fs/promises';  
  
async function example() {  
  try {  
   const content = '\nSome content appended wit async/await!';  
   await fs.appendFile('./append.txt', content);  
  } catch (err) {  
   console.error(err);  
  }  
}  
  
example();

```

### Reading files

All of the methods read the full content of the file in memory before returning data. This means that big files are going to have a major impact on memory consumption and speed of execution of the program. In this case, a better option is to read the file content using streams.

```js
import fs from 'node:fs';  
  
fs.readFile('./test.txt', 'utf8', (err, data) => {  
  if (err) {  
   console.error(err);  
  
   return;  
  }  
  console.log(data);  
})  
  
// Synchronous  
  
try {  
  const data = fs.readFileSync('./test.txt', 'utf8');  
  console.log(data);  
} catch (err) {  
  console.error(err);  
}  
  
// promise  

import fs from 'node:fs/promises';
  
try {  
  const data = await fs.readFile('/Users/joe/test.txt', { encoding: 'utf8' });  
  console.log(data);  
} catch (err) {  
  console.log(err);  
}

```