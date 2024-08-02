
Tags: [[TypeScript]]

---
 
### Merging with existing interface

```ts
interface Person {  
    name: string;  
    getDetails(): string;  
}  
  
interface DogOwner {  
    dogName: string;  
    getDogDetails(): string;  
}  
  
interface Person {  
    age: number;  // adding another prop to the existing interface
}  
  
const person: Person = {  
    name: 'john',  
    age: 30,  // prop added to the instance
    getDetails() {  
        return `Name: ${this.name}, Age: ${this.age}`;  
    }  
}  
  
console.log(person.getDetails());
```

### Extending new interface with the existing one (without modifying it)

```ts
interface Person {  
    name: string;  
    getDetails(): string;  
}  
  
interface DogOwner {  
    dogName: string;  
    getDogDetails(): string;  
}  
  
interface Person {  
    age: number;  
}  
  
const person: Person = {  
    name: 'john',  
    age: 30,  
    getDetails() {  
        return `Name: ${this.name}, Age: ${this.age}`;  
    }  
}  
  
interface Employee extends Person {  // 'extend' keyword
    employeeId: number;  
}  
  
const employee: Employee = {  
    name: 'jane',  
    age: 25,  
    employeeId: 123,  
    getDetails() {  
        return `Name: ${this.name}, Age: ${this.age}, 
		        Employee ID:${this.employeeId}`;  
    }  
}  
  
console.log(employee.getDetails());
```

### Extending new interface with multiple ones

```ts
interface Person {  
    name: string;  
    getDetails(): string;  
}  
  
interface DogOwner {  
    dogName: string;  
    getDogDetails(): string;  
}  
  
interface Person {  
    age: number;  
}  
  
interface Manager extends Person, DogOwner{  // extend by adding after ','
    managePeople(): void;  
}  
  
const manager: Manager = {  
    name: 'bob',  
    age: 35,  
    dogName: 'rex',  
    getDetails() {  // can access from Person
        return `Name: ${this.name}, Age: ${this.age}`;  
    },  
    getDogDetails() {  // can access from DogOwner
        return `Name: ${this.dogName}`;  
    },  
    managePeople() {  
        console.log('Managing people')  
    },  
}  
  
manager.managePeople();
```