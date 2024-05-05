Equality narrowing is a form of type narrowing that occurs when you use equality checks like `===` or `!==`

```ts
type Dog = { type: 'dog'; name: string; bark: () => void };  
type Cat = { type: 'cat'; name: string; meow: () => void };  
type Animal = Dog | Cat;  
  
function makeSound(animal: Animal): void {  
    if (animal.type === 'dog') {  
       animal.bark();  
    } else {  
       animal.meow();  
    }  
}  
  
const dog: Dog = { type: 'dog', name: 'rex', bark: () => console.log('bark') };  
const cat: Cat = { type: 'cat', name: 'garfield', meow: () => console.log('meow') };  
  
makeSound(dog); // bark
makeSound(cat); // meow
```


We can achieve that by using 'in' keyword in conditional statement. It is used to narrow down the type of a variable. It checks if a property or method exists on an object. If it exists, TS will narrow the type to the one that has this property.

```ts
type Dog = { type: 'dog'; name: string; bark: () => void };  
type Cat = { type: 'cat'; name: string; meow: () => void };  
type Animal = Dog | Cat;

function makeSound(animal: Animal) {  
  if ('bark' in animal) {  
    // TypeScript knows that `animal` is a Dog in this block  
    animal.bark();  
  } else {  
    // TypeScript knows that `animal` is a Cat in this block  
    animal.meow();  
  }  
}
```