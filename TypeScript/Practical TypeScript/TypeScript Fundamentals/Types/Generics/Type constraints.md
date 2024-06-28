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

---

#### Specific prop example

Although we are looking for a prop that exists in a specific type:

```ts
type Car = {  
    brand: string;  
    model: string;  
};  
  
const car: Car = {  
    brand: 'ford',  
    model: 'mustang'  
};  
  
type Product = {  
    name: string;  
    price: number;  
};  
  
const product: Product = {  
    name: 'shoes',  
    price: 1.99  
};  
  
type Student = {  
    name: string;  
    age: number;  
};  
  
const student: Student = {  
    name: 'peter',  
    age: 20  
};  
  
function printName<T extends Student | Product>(input: T): void {  
    console.log(input.name);  
}  
  
printName(student);  
printName(product);
```

and technically it is correct to combine the types that we are looking for, we can narrow it down to the exact shape that we are expecting like so:

```ts
// after extends we pass in the object with a specified property and type
function printName<T extends { name: string }>(input: T): void {  
    console.log(input.name);  
}  
  
printName(student);
printName(product);
printName(car); // here TS throws error, no such prop in type Car
```