do...while loop iterates until the condition passes but always executes at least once with the code from the do{} block first

example:

`const cats = ['Pete', 'Biggles', 'Jasmine'];`

`let myFavoriteCats = 'My cats are called ';`

`let i = 0;`

`do {`
	`if (i === cats.length - 1) {`
		`myFavoriteCats += and ${cats[i]};`
	`} else {`
		`myFavoriteCats += ${cats[i]}, `
	`}`
	
	`i++;`
`} while (i < cats.length);`

`console.log(myFavoriteCats); // "My cats are called Pete, Biggles, and Jasmine."`