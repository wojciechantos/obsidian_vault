
```ts
let prices: number[] = [100, 75, 42];  
// prices.push = 'five'; throws an error; assigning string to type number
  
let fruit: string[] = ['apple', 'orange', 'banana'];
  
let randomValues: [] = []; // this means the randomValues is ALWAYS AN EMPTY ARRAY and will throw an error when trying to add anything to it

let emptyValues = []; // any[]!

let array: (string | boolean)[] = ['apple', true]; // union type
```

