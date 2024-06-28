If we are more familiar with the type than TS we can assign it to the new instance with type 'any' using the keyword 'as': 

```ts
let someValue: any = 'this is some value';  
  
let strLength: number = (someValue as string).length;  //here we use 'as'
  
type Bird = {  
    name: string,  
}  
  
let birdString = '{"name": "Eagle"}';  
let dogString = '{"breed": "Poodle"}';  
  
let birdObject = JSON.parse(birdString);  
let dogObject = JSON.parse(birdString);  
  
let bed = birdObject as Bird; //here we use 'as'
```