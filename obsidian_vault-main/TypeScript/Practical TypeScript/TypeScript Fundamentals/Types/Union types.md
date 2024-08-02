
Tags: [[TypeScript]]

---
 
Union types in TS allow to set up multiple possible types to the variable.


```ts
let response: string | number | boolean = true;

let responseStatus: 'success' | 'pending' | 'error' = 'success';

responseStatus = //editor will hint with the provided types ('success' | 'pending' | 'error' );

responseStatus = 'awaiting' // will throw an error; type not declared as one of the allowed ones
```

By assigning only a string type to the foundBook variable, the TS would throw an error in the console.log line, because the result of a loop can be undefined, for example if the searched book would not exist in the searched array. When assigned like this, there is no more error and the TS will also auto suggest the optional chaining.

```ts
const books = ['1984', 'Brave New World', 'Fahrenheit 451'];  

let foundBook: string | undefined;
  
for (let book of books) {  
    if(book === '1984') {  
        foundBook = book;  
  
        foundBook = foundBook.toUpperCase();  
        break;  
    }  
}  
  
console.log(foundBook?.length);
```