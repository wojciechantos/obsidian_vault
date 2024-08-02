
Tags: [[JavaScript]]

---
 
filter() - returns new array with items filtered with given condition 
`const cats = ['Leopard', 'Serval', 'Jaguar', 'Tiger', 'Lion'];`

`function lcat(cat) {
	`return cat.startsWith('L');`
`}`

`const filtered = cats.filter(lcat);`

`console.log(filtered); // ['Leopard', 'Lion']`