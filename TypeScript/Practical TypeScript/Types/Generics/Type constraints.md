Type constraints allow us to specify the generic types by using the `extends` keyword.

```ts
function processValue<T extends string | number>(value: T): T {  
    console.log(value);  
    return value;  
}  
  
processValue('hello');  
processValue(12);  
 
processValue(true); // Error: Argument of type boolean is not assignable to                             parameter of type string | number 
```