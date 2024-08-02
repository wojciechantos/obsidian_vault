
Tags: [[TypeScript]]

---
 
In JavaScript, classes are used as a blueprint for creating an object. They encapsulate data with code to manipulate that data. Classes in JS support inheritance and can be used to create more complex data structures.


A constructor in a class is a special method that gets called when a new instance of a class is created:

```ts
class Book {
	constructor()
}
```

 It is often used to set the initial state of the object:
 
```ts
class Book {
	constructor(title, author) {
		this.title = title;
		this.author = author;
	}
}

const deepWork = new Book('Deep Work', 'Cal Newport');
console.log(deepWork); // { title: 'Deep Work', author: 'Cal Newport' }
```

---

### Classes in TS

In the context of type annotations we need to not only specify the types for the constructor method params, but also for the class properties themselves:

```ts
class Book {  
    title: string; // here we annotate the types for the class
    author: string;  // here we annotate the types for the class
	
	// and here for the constructor params
    constructor(title: string, author: string) {  
       this.title = title;  
       this.author = author;  
    }  
}  
  
const deepWork = new Book('Deep Work', 'Cal Newport');  
console.log(deepWork); // { title: 'Deep Work', author: 'Cal Newport' }
```