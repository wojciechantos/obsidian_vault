
Tags: [[JavaScript]]

---
 
map() - returns new array with items modified with given task 

``` js
const cats = ['Leopard', 'Serval', 'Jaguar', 'Tiger', 'Lion'];

function toUpper(string) {
	return string.toUpperCase();
}

const upperCats = cats.map(toUpper);

console.log(upperCats); // ['Leopard', 'Serval', 'Jaguar', 'Tiger', 'Lion']
```

