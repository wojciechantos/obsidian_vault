
Tags: [[TypeScript]]

---
 
Interface type is used to describe the shape of an object.

```ts
interface Book {  // notice no '=' sign after name!
    readonly isbn: number;  // readonly blocks possibility to modify
    title: string;          // props are ended with semicolon ';'
    author: string;  
    genre?: string;         // optional params are marked with '?'
}  
  
const deepWork: Book = {  
    isbn: 123,  
    title: "deep work",  
    author: 'cal newport',  
    // genre: 'self-help' - optional property as marked in the interface  
}  
  
// deepWork.isbn = 333; - error, isbn is a readonly property
```

### Methods

The interface methods can be set as follows:

```ts
interface Book {  
    readonly isbn: number;  
    title: string;  
    author: string;  
    genre?: string;  
    // method  
    printAuthor(): void,  
    printTitle(message: string): string  
}  
  
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
    }  
}  
  
deepWork.printAuthor();  
  
const result = deepWork.printTitle('is an awesome book');  
  
console.log(result);
```