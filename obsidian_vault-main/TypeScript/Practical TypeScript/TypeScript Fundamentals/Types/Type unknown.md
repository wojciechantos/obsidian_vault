
Tags: [[TypeScript]]

---
 
Type unknown is similar to the type any an can be literally anything, but the difference is that with type unknown we must do some type-checking.

For example:
```ts
let unknownValue: unknown;  
  
unknownValue = 'hello world';  
unknownValue = [1, 2, 3];  
unknownValue = 43;  
  
const someValue = unknownValue.toFixed(2); // TS returns error
  
if (typeof unknownValue === 'number') {  
    unknownValue.toFixed(2);               // Now TS is ok with that
}
```

---
### Practical example

Imagine that we expect some 3rd party library to respond with some error message for example. We don't know for sure if its going to be an instance of an Error or anything else.

```ts
function runSomeCode() {  
    const random = Math.random();  
  
    if (random < 0.5) {  
       throw new Error('Something went wrong!');  
    } else {  
       throw 'some error';  
    }  
}  

// Here TS will throw error on 'error' because it is type 'unknown'
try {  
    runSomeCode();  
} catch (error) {
	console.log(error.message); 
}

// Here we do type-checking with instanceof and there is no more error
try {  
    runSomeCode();  
} catch (error) {  
    if (error instanceof Error) {  
       console.log(error.message);  
    } else {  
       console.log(error);  
       console.log('there was an error...');  
    }  
}
```