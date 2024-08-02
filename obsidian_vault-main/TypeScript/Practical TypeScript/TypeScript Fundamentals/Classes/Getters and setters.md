
Tags: [[TypeScript]]

---
 
Getters and setters are special methods in a class that allow you to control how a property is accessed and modified. They are used like properties, not methods, so the parentheses are not needed to call them. Here is a getter example:

```ts
class Book {  
    private checkedOut: boolean = false;  
  
    constructor(readonly title: string, public author: string) {}  
    
    get info() {  
       return `${this.title} by ${this.author}`;  
    }

}  
  
const deepWork = new Book('Deep Work', 'Cal Newport');  
console.log(deepWork.info); // Deep Work by Cal Newport, notice no parentheses!
```

Here is a setter example:

```ts
class Book {  
    private checkedOut: boolean = false;  
  
    constructor(readonly title: string, public author: string) {  
    }  
  
    set checkOut(checkOut: boolean) {  
       this.checkedOut = checkOut;  
    }  
}  
  
const deepWork = new Book('Deep Work', 'Cal Newport');  
deepWork.checkOut = true; // we change the value with the setter  
console.log(deepWork); // {checkedOut: true, title: 'Deep Work', author: 'Cal Newport'}
```