
Metoda reduce() w języku JavaScript służy do redukcji tablicy do jednej wartości. Główna idea działania metody reduce jest taka, że dla każdego elementu tablicy jest wywoływana funkcja zwrotna, a jej wynik jest przechowywany w akumulatorze. Akumulator służy jako "pamięć" dla poprzednich wyników, dlatego też na koniec działania metody reduce otrzymujemy jedną wartość końcową.
Przykład użycia metody reduce(), do zsumowania wszystkich liczb w tablicy:

```
let numbers = [1, 2, 3, 4];

let sum = numbers.reduce((accumulator, currentValue) => {
	return  accumulator + currentValue;
}, 0);

console.log(sum()); // 10
```


