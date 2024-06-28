
We can describe the shape of the class by implementing the interface with the `implements` keyword, like this:

```ts
interface IPerson {  
    name: string;  
    age: number;  
    greet(): void;  
}  
  
class Person implements IPerson {  
    constructor(public name: string, public age: number) {}  
    
    greet(): void {  
       console.log(
	       `Hello, my name is ${this.name} and I'm ${this.age} years old`
		);  
    }  
}  
  
const person = new Person('Johannes', 34);  
  
person.greet(); // Hello, my name is Johannes and I'm 34 years old
```