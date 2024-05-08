
By default everything in the classes is reachable (`public`) from the outside. But, we can 'hide' the desired properties with the `private` keyword.

```ts
class Book {  
    readonly title: string;  
    author: string;  
    private checkedOut: boolean = false; // here we set the checkedOut as private
    constructor(title: string, author: string) {  
       this.title = title;  
       this.author = author;  
    }  
}  
  
const deepWork = new Book('Deep Work', 'Cal Newport');
deepWork.checkedOut; // Error: Property checkedOut is private and only accessible within class Book
```

As the TS error says - from now on the `checkedOut` property can be accessed directly only inside the Book class. But we can set up some kind of method which we're gonna call from the outside:

```ts
class Book {  
    readonly title: string;  
    author: string;  
    private checkedOut: boolean = false; // here  
  
    constructor(title: string, author: string) {  
       this.title = title;  
       this.author = author;  
    }  
  
    checkOut() {  
       this.checkedOut = true; // The prop is reachable from within the class  
    }  
}  
  
const deepWork = new Book('Deep Work', 'Cal Newport');  
deepWork.checkOut(); // here we call the method to change the prop value  
console.log(deepWork); // {title: 'Deep Work', author: 'Cal Newport',                                       checkedOut: true}
```

---

#### Constructor shortcut

By using one of the modifiers: 
- readonly
- public
- private
we can omit the declaration of the values with this:

```ts
constructor(valueOne:string, valueTwo:boolean) {
	this.valueOne = valueOne;
	this.valueTwo = valueTwo;
}
```

and simplify the constructor like this:

```ts
constructor(
	readonly valueOne: string, 
	public valueTwo: string, 
	private valueThree: number
) {} // here we don't need to assign them
```


The whole class example will look like this:

```ts
class Book {  
    private checkedOut: boolean = false;  
  
    constructor(
	    readonly title: string, 
	    public author: string, 
	    private someValue: number
	) {}  
	    
    getSomeValue() {  
       return this.someValue;  
    }  
}  
  
const deepWork = new Book('Deep Work', 'Cal Newport', 45);  
console.log(deepWork.getSomeValue());  // 45
```

