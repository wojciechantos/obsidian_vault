
Tags: [[TypeScript]]

---
 
Tuples are a special types that specifically describe with an array how the value should look like.

```ts
let person: [string, number] = ['john', 25];
```

The value of 'person' needs to be specifically an array with length of 2, it needs to have two elements with corresponding types and also in a specific order as described in tuple. It can be extended but the value always needs to exactly match the tuple shape and length.

Practical example:

```ts
function getPerson(): [string, number] {  
    return ['john', 25];  
}  
  
let randomPerson = getPerson();  
console.log(randomPerson[0]);  // 'john'
console.log(randomPerson[1]);  // 25
```

---
Another example:

```ts
let date: [number, number, number] = [12, 17, 2001];

console.log(date); // 12, 17, 2001

// date can be modified by instances
date.push(34) // or any other array method

console.log(date); //  12, 17, 2001, 34
```

To block the possibility of modifying date tuple, the readonly can be used

```ts
let date: readonly [number, number, number] = [12, 17, 2001];
```

Also the optional params are possible in tuples;

```ts
let susan: [string, number?] = ['susan']; // no error, second prop is optional
```