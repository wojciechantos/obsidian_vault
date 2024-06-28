```ts
function pair<T, U>(param1: T, param2: U): [T, U] {  
    return [param1, param2];  
}  
  
let result = pair<number, string>(123, 'hello');  
  
console.log(result); // [123, 'hello']
```