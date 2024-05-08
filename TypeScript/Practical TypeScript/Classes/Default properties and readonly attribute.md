
### Default properties

In classes, the properties can have the default values set as below:

```ts
class Book {  
    title: string;  
    author: string;  
    checkedOut: boolean = false;  
    // checkedOut = false;  this is also valid, TS will infer the type                                       automatically
	
    constructor(title: string, author: string) {  
       this.title = title;  
       this.author = author;  
    }  
}  
  
const deepWork = new Book('Deep Work', 'Cal Newport');  
console.log(deepWork.checkedOut); // false
```

so trying to assign new value to the `checkedOut` prop with a type different than boolean, will result an error:

```ts
class Book {  
    title: string;  
    author: string;  
    checkedOut: boolean = false;  
  
    constructor(title: string, author: string) {  
       this.title = title;  
       this.author = author;  
    }  
}  
  
const deepWork = new Book('Deep Work', 'Cal Newport');  
deepWork.checkedOut = 'yes'; // TS Error: string cannot be assigned to boolean  
console.log(deepWork.checkedOut);
```

---

### Readonly attributes

We can also use readonly keyword to block the possibility to modify specific props inside the class:

```ts
class Book {  
    readonly title: string; // here we set the readonly attribute
    author: string;  
    checkedOut: boolean = false;  
  
    constructor(title: string, author: string) {  
       this.title = title;  
       this.author = author;  
    }  
}  
  
const deepWork = new Book('Deep Work', 'Cal Newport');  
deepWork.title = 'something else'; // Error: Cannot assign to title because it                                         is a read-only property.  
console.log(deepWork.title);
```