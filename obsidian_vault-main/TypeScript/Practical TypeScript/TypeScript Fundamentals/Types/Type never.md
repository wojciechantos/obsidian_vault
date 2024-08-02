
Tags: [[TypeScript]]

---
 
```ts
// let someValue: never = 0; // cannot assign any value!

type Theme = 'light' | 'dark';  
  
function checkTheme(theme: Theme): void {  
    if (theme === 'light') {  
       console.log('light theme');  
       return;  
    }  
  
    if (theme === 'dark') {  
       console.log('dark theme');  
       return;  
    }  
  
    theme; // theme will be type never, because all cases are handled
}  
  
enum Color {  
    Red,  
    Blue,  
    Green  
}  
  
function getColorName(color: Color) {  
    switch (color) {  
       case Color.Red:  
          return 'Red';  
       case Color.Blue:  
          return 'Blue';  
    }  
}  
  
console.log(getColorName(Color.Red));  
console.log(getColorName(Color.Blue));  
console.log(getColorName(Color.Green)); // this will be undefined because it is not handled with the switch statement
```

here is a correct handling:

```ts
enum Color {  
    Red,  
    Blue,  
    Green  
}  
  
function getColorName(color: Color) {  
    switch (color) {  
       case Color.Red:  
          return 'Red';  
       case Color.Blue:  
          return 'Blue';  
       case Color.Green:  
          return 'Green';  
       default:  
          // at build time  
          let unexpectedColor: never = color;  
          // at runtime  
          throw new Error(`Unexpected color value: ${color}`);  
    }  
}  
  
console.log(getColorName(Color.Red));  
console.log(getColorName(Color.Blue));  
console.log(getColorName(Color.Green));
```