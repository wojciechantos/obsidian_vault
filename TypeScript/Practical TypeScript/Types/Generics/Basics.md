Generics in TS are a way to create reusable code components that work with a variety of types as opposed to a single one.

With generics we can pass any type to the 'T' type declaration as presented below. It makes the functions, interfaces, classes etc. reusable, because they are no more limited to one previously declared type.

```ts
function genericFunction<T>(args: T): T {  
    return args;  
}  
  
const someStringValue = genericFunction<string>('hello');
const someNumberValue = genericFunction<number>(2);  
  
interface GenericInterface<T> {  
    value: T;  
    getValue: () => T;  
}  
  
const genericString: GenericInterface<string> = {  
    value: 'some value',  
    getValue() {  
       return this.value;  
    }  
};
```


---
#### Promise example

Here we declare the async function and we need to use a generic Promise instance with the string as type in order to be able to return a string.

```ts
async function someFunc(): Promise<string> {  
    return 'hello';  
}  
  
const result = someFunc();
```


Otherwise, if we declare async function only with string type as return as follows: 

```ts
async function someFunc(): string{  
    return 'hello';  
}  
  
const result = someFunc();
```

the TS will complain with the following error:

```ts
TS1064: The return type of an async function or method must be the global Promise<T> type. Did you mean to write Promise<string>?
```

---

#### Example 2

Here we have an example of a function, that instead of writing it like this:

```ts
function generateStringArray(length: number, value: string): string[] {  
  let result: string[] = [];  
  result = Array(length).fill(value);  
  return result;  
}  
```

we can write as a generic function. It simply allows us to set the value type to anything, and set it when the function is assigned:

```ts
function createArray<T>(length: number, value: T): Array<T> {  
    let result: T[] = [];  
    result = Array(length).fill(value);  
    return result;  
}  
  
let arrayStrings = createArray<string>(10, 'hello');  
let numberStrings = createArray<number>(10, 20);  
  
console.log(arrayStrings);  
console.log(numberStrings);
```