
Tags: [[TypeScript]]

---
 
Before the given logic is going to be executed the 'type guard' should be set to make sure that the given parameter is a proper type. Otherwise, the given error will be displayed:

`TS2362: The left-hand side of an arithmetic operation must be of type any, number, bigint or an enum type.`

In order to prevent that, here is the type guard example:

```ts
function processInput(input: string | number) {  
    if (typeof input === "number") {  
        console.log(input * 2);  
    } else {  
        console.log(input.toUpperCase());  
    }  
}  
  
processInput(10);  
processInput('example');
```
#### Example

```ts
type ValueType = string | number | boolean;  
  
let value: ValueType;  
const random = Math.random();  
value = random < 0.33 ? 'Hello' : random < 0.66 ? 123.456 : true;  
  
function checkValue(value: ValueType): void {  
    if (typeof value === 'string') {  
       console.log(value.toLowerCase());  
       return;  
    } else if (typeof value === 'number') {  
       console.log(value.toFixed(2));  
       return;  
    } else {  
       console.log(`boolean: ${ value }`);  
    }  
}  
  
checkValue(value);
```
