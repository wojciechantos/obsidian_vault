
- [[#VAR rules|VAR rules]]
- [[#let, const, class, function rules|let, const, class, function rules]]
- [[#Using a block statement to encapsulate data|Using a block statement to encapsulate data]]


https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block


A **block statement** is used to group zero or more statements. The block is delimited by a pair of braces ("curly brackets") and contains a list of zero or more statements and declarations.

```
var x = 1;
let y = 1;

if (true) {
  var x = 2;
  let y = 2;
}

console.log(x);
// Expected output: 2

console.log(y);
// Expected output: 1

```


## VAR rules

Variables declared with `var` or created by [function declarations](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function) in non-strict mode **do not** have block scope.

```
var x = 1;

{
var x = 2;
}
console.log(x); // 2
```

This logs 2 because the `var x` statement within the block is in the same scope as the `var x` statement before the block.



## let, const, class, function rules

Identifiers declared with [`let`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let), [`const`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const), and [`class`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/class) do have block scope.

```
let x = 1;
{
  let x = 2;
}
console.log(x); // 1
```


## Using a block statement to encapsulate data

```
let sector;
{
  // These variables are scoped to this block and are not
  // accessible after the block
  const angle = Math.PI / 3;
  const radius = 10;
  sector = {
    radius,
    angle,
    area: (angle / 2) * radius ** 2,
    perimeter: 2 * radius + angle * radius,
  };
}
console.log(sector);
// {
//   radius: 10,
//   angle: 1.0471975511965976,
//   area: 52.35987755982988,
//   perimeter: 30.471975511965976
// }
console.log(typeof radius); // "undefined"
```

