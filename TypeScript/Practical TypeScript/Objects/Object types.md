```ts
let book = { title: 'book', cost: 20 };  
let pen = { title: 'pen', cost: 10 };  
let notebook = { title: 'notebook' };  
```

This will throw an error in the array since notebook does not match the object shape (missing cost property):

```ts
let items: { title: string, cost: number }[] = [book, pen, notebook];
```


Adding the ? symbol to the object shape annotation property will allow to add a cost property as an optional param :

```ts
let items: { title: string, cost?: number }[] = [book, pen, notebook];
```

Adding readonly the object shape annotation will prevent from reassigning values:

```ts
let items: { readonly title: string, cost?: number }[] = [book, pen, notebook];
```

so this will throw an error :

```ts
items[0].title = 'new book';
```

---
Challange

```ts
let bike: { brand: string, year: number } = { brand: 'yamaha', year: 2010 };  
// bike.year = 'old'; - Error: missing property  
  
let laptop: { brand: string, year: number } = { brand: 'Dell', year: 2020 };  
// let laptop2: { brand: string, year: number } = { brand: 'HP' }; - Error: missing property  
  
let product1 = { title: 'shirt', price: 20 };  
let product2 = { title: 'pants' };  
let products: { title: string; price?: number  }[] = [product1, product2];  
// products.push({ title: 'shoes', price: 'expensive' }); - Error: price must be of type number, although its optional
```
