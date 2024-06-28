```ts
// try {  
//  throw 'this is an error';  
// } catch (error) {  
//  if (error instanceof Error) {  
//     console.log(`Caught an Error object: ${ error.message }`);  
//  } else {  
//     console.log('unknown error...');  
//  }  
// }  
  
function checkInput(input: Date | string): string {  
    if (input instanceof Date) {  
       return input.getFullYear().toString();  
    }  
    return input;  
}  
  
const year = checkInput(new Date());  
const random = checkInput('2024-05-05');  
  
console.log(year); // '2024'
console.log(random); // '2024-05-05'
```