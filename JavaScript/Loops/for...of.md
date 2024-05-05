for...of - a loop to go through a collection (Array, Set, Map)

example: 

`const cats = ['Leopard', 'Serval', 'Jaguar', 'Tiger', 'Lion'];`

`for (const cat of cats) {
	`console.log(cat);`
`}`

Same task can be accomplished with `for` loop:

`for (let i = 0; i < cats.length; i++) {`
	`console.log(cats[i])`
`}`