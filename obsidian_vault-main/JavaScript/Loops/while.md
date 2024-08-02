
Tags: [[JavaScript]]

---
 
while loop iterates until the condition passes

example:

`const cats = ['Pete', 'Biggles', 'Jasmine'];`

`let myFavoriteCats = 'My cats are called ';`

`let i = 0;`

`while (i < cats.length) {`
	`if (i === cats.length - 1) {`
		`myFavoriteCats += and ${cats[i]};`
	`} else {`
		`myFavoriteCats += ${cats[i]}, `
	`}`
	
	`i++;`
`}`

`console.log(myFavoriteCats); // "My cats are called Pete, Biggles, and Jasmine."`