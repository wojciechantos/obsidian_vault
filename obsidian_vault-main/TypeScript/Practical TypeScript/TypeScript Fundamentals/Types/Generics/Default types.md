
Tags: [[TypeScript]]

---
 
If we don't know what type the expected object will be, we can set the default type of the generic.

Consider this example:

```ts
interface StoreData<T> {
    data: T[];  
}  
  
const storeNumbers: StoreData<number> = {  
    data: [1, 2, 3, 4]  // here it's not a problem
};  
  
const randomStuff: StoreData = {  
    data: ['random', 12]  
 	    // but here without annotating the type, TS would throw an error,                   because it expects type to be specified
};
```

To resolve the issue, we can annotate the default type directly, like:

```ts
interface StoreData<T> {
    data: T[];  
}  
  
const storeNumbers: StoreData<number> = {  
    data: [1, 2, 3, 4],
};  
  
const randomStuff: StoreData<any> = {  // here we declare the generic type
    data: ['random', 12],
};
```

or, we can specify it in the generic, like:

```ts
interface StoreData<T = any> { // here we pass 'any' as a default type
    data: T[];  
}  
  
const storeNumbers: StoreData<number> = {  
    data: [1, 2, 3, 4]  // here it's not a problem
};  
  
const randomStuff: StoreData = {  
    data: ['random', 12]  // and here it also works!
};
```