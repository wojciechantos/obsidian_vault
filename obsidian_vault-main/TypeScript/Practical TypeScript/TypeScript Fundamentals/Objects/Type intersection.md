
Tags: [[TypeScript]]

---
 
Type intersection is used to extend one type with some additional properties. There are two ways of doing it:

### Inline

```ts
type Book = { id: number, title: string, price: number };  
  
const book1: Book = {  
    id: 1,  
    title: 'how to cook a dragon',  
    price: 15,  
}  
  
const book2: Book = {  
    id: 2,  
    title: 'the secret life of unicorns',  
    price: 25,  
}  
  
const discountedBook: Book&{ discount: number } = {  // here we extend the type
    id: 3,  
    title: 'Gnomes vs. Goblins: The Ultimate Guide',  
    price: 35,  
    discount: 0.15,  
}
```

### or by defining new type

```ts
type Book = { id: number, title: string, price: number };  
  
type DiscountedBook = Book&{ discount: number };  
  
const book1: Book = {  
    id: 1,  
    title: 'how to cook a dragon',  
    price: 15,  
}  
  
const book2: Book = {  
    id: 2,  
    title: 'the secret life of unicorns',  
    price: 25,  
}  
  
const discountedBook: DiscountedBook = {  
    id: 3,  
    title: 'Gnomes vs. Goblins: The Ultimate Guide',  
    price: 35,  
    discount: 0.15,  
}
```