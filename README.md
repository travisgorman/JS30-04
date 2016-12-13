# Array Cardio Day 1
JavaScript 30 Day #4 project — Solve 9 data manipulation problems with Array methods

___
QUESTION #1 filter the list of inventors for those who were born in the 1500s:

```js
	const now = new Date();
	const thisYear = now.getFullYear();
    
    const bornIn1500s = inventors.filter(inventor => 
      thisYear - inventor.year >= 417 &&
      thisYear - inventor.year <= 518);

    console.log(`${bornIn1500s.length} inventors were born in the 1500's:`)
    bornIn1500s.forEach(inventor => 
      console.log( inventor.first, inventor.last + " born in " + inventor.year)) 
```

To find the inventors born in the 1500's, I see how their birth year compares with the current year. They need to have been born at least 417 years ago, but not more than 518 years ago. 

___
QUESTION #2 Give us an array of the inventory first and last names:

```js
	const inventorNames = inventors.map(i => i.first + ", "+ i.last);

	console.log( inventorNames )
```

`inventorNames` returns an array of strings. I'm concatenating the `last` to `first` with a comma and space in between the two.

___
