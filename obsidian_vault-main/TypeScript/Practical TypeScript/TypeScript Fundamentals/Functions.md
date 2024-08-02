
Tags: [[TypeScript]]

---

Function parameters need to have their types set as well as the function return.

```ts
function calculateDiscount(price: number): number {  
    const hasDiscount = true;  
  
    if(hasDiscount) {  
        return 'Discount applied'; 
	    // This wil result the error, TS expects the 'return' to be of type                 number as declared above 
    }  
  
   return price * 0.9;  
}  
  
const finalPrice = calculateDiscount(200);
```


### Optional parameters

```ts
function calculatePrice(price: number, discount?: number): number { 
/* Because the 'discount' param is optional, we cannot set return as:
	return price - discount;
	
	because TS will return error as the discount can be undefined
	We can set the optional parameter as follows:
*/	
    return price - (discount || 0);  
}  
  
let priceAfterDiscount = calculatePrice(100, 20);
```

### Examples

```ts
const names: string[] = ['John', 'Mike', 'Janette', 'Javier'];  
  
function isNameInList(name: string): boolean {  
    return names.includes(name);  
}  
  
let nameToCheck: string = 'Javier';  
  
if (isNameInList(nameToCheck)) {  
    console.log(`${nameToCheck} is in the list`);  
} else {  
    console.log(`${nameToCheck} is not in the list`);  
}
```


### Rest parameter

```ts
function sum(message: string, ...numbers:number[]): string {  
    const doubled = numbers.map((num: number): number => num * 2);  
    console.log(doubled);  
  
    let total = numbers.reduce((previous, current) => {  
        return previous + current;  
    }, 0);  
  
    return `${message}${total}`;  
}  
  
let result = sum('The total is : ', 1, 2, 3, 4, 5);  
  
console.log(result);
```