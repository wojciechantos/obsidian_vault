
Tags: [[TypeScript]]

---
 
Methods as props in interface can be set with a few different ways:


```ts
interface Book {  
    readonly isbn: number;  
    title: string;  
    author: string;  
    genre?: string;  
    // method  
    printAuthor(): void;  
    printTitle(message: string): string;  
    // alternative method setting  
    printSomething: (someValue: number) => number;  
}  

/* OPTION #1 */

const deepWork: Book = {  
    isbn: 123,  
    title: "deep work",  
    author: 'cal newport',  
    genre: 'self-help',  
    printAuthor() {  
        console.log(this.author);  
    },  
    printTitle(message) {  
        return `${this.title} ${message}`;  
    },  
    // first option  
	printSomething: function(someValue) {  
	    return someValue;  
	}
}  
  
console.log(deepWork.printSomething(34));

/* OPTION #2 */

const deepWork: Book = {  
    isbn: 123,  
    title: "deep work",  
    author: 'cal newport',  
    genre: 'self-help',  
    printAuthor() {  
        console.log(this.author);  
    },  
    printTitle(message) {  
        return `${this.title} ${message}`;  
    },  
    //second option  
	printSomething: (someValue) => {  
    // arrow function this is capturing the global this, so we cannot access it         straight forward  like below
    // console.log(this.author)    
    
    console.log(deepWork.author)  
  
    return someValue;  
	}
}  

console.log(deepWork.printSomething(34));

/* OPTION #3 */

const deepWork: Book = {  
    isbn: 123,  
    title: "deep work",  
    author: 'cal newport',  
    genre: 'self-help',  
    printAuthor() {  
        console.log(this.author);  
    },  
    printTitle(message) {  
        return `${this.title} ${message}`;  
    },  
    // third option  
    printSomething(someValue) {  
        return someValue;  
    }
  
console.log(deepWork.printSomething(34));

/* OPTION #4 */

const deepWork: Book = {  
    isbn: 123,  
    title: "deep work",  
    author: 'cal newport',  
    genre: 'self-help',  
    printTitle(message) {  
        return `${this.title} ${message}`;  
    },  
    // fourth option  
    printAuthor: () => {  
        console.log(deepWork.author);  
    }  
}  
  
console.log(deepWork.printAuthor());
```

### Example

```ts
interface Computer {  
    readonly id: number,  
    brand: string,  
    ram: number,  
    storage?: number  
    upgradeRam(amount: number): number,  
}  
  
const laptop: Computer = {  
    id: 1,  
    brand: 'macbook',  
    ram: 16,  
    upgradeRam(amount: number): number {  
        this.ram += amount;  
        return this.ram;  
    }  
}  
  
laptop.storage = 256;  
  
console.log(laptop.upgradeRam(8)); // 24
  
console.log(laptop); 
// { id: 1, brand: 'macbook', ram: 24, storage: 256, upgradeRam: f() }
```