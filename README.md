# Array Cardio Day 1
JavaScript 30 Day #4 project — Solve 9 data manipulation problems with Array methods

___
##Data
These are the data sets being worked on in

```js
const inventors = [
      { first: 'Albert', last: 'Einstein', year: 1879, death: 1955 },
      { first: 'Isaac', last: 'Newton', year: 1643, death: 1727 },
      { first: 'Galileo', last: 'Galilei', year: 1564, death: 1642 },
      { first: 'Marie', last: 'Curie', year: 1867, death: 1934 },
      { first: 'Johannes', last: 'Kepler', year: 1571, death: 1630 },
      { first: 'Nicolaus', last: 'Copernicus', year: 1473, death: 1543 },
      { first: 'Max', last: 'Planck', year: 1858, death: 1947 }
    ];

    const flavours = ['Chocolate Chip', 'Kulfi', 'Caramel Praline', 'Chocolate', 'Burnt Caramel', 'Pistachio', 'Rose', 'Sweet Coconut', 'Lemon Cookie', 'Toffeeness', 'Toasted Almond', 'Black Raspberry Crunch', 'Chocolate Brownies', 'Pistachio Almond', 'Strawberry', 'Lavender Honey', 'Lychee', 'Peach', 'Black Walnut', 'Birthday Cake', 'Mexican Chocolate', 'Mocha Almond Fudge', 'Raspberry'];

    const people = ['Beck, Glenn', 'Becker, Carl', 'Beckett, Samuel', 'Beddoes, Mick', 'Beecher, Henry', 'Beethoven, Ludwig', 'Begin, Menachem', 'Belloc, Hilaire', 'Bellow, Saul', 'Benchley, Robert', 'Benenson, Peter', 'Ben-Gurion, David', 'Benjamin, Walter', 'Benn, Tony', 'Bennington, Chester', 'Benson, Leana', 'Bent, Silas', 'Bentsen, Lloyd', 'Berger, Ric', 'Bergman, Ingmar', 'Berio, Luciano', 'Berle, Milton', 'Berlin, Irving', 'Berne, Eric', 'Bernhard, Sandra', 'Berra, Yogi', 'Berry, Halle', 'Berry, Wendell', 'Bethea, Erin', 'Bevan, Aneurin', 'Bevel, Ken', 'Biden, Joseph', 'Bierce, Ambrose', 'Biko, Steve', 'Billings, Josh', 'Biondo, Frank', 'Birrell, Augustine', 'Black Elk', 'Blair, Robert', 'Blair, Tony', 'Blake, William'];

```

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

To find the inventors born in the 1500's, I look at how their birth year compares with the current year. They need to have been born at least 417 years ago, but not more than 518 years ago. I return the objects meeting that criteria with `filter`

___
##QUESTION #2 — Make an array of the inventors first and last names:

```js
	const inventorNames = inventors.map(i => i.first + ", "+ i.last);
```

`inventorNames` returns an array of strings. I'm concatenating the `last` to `first` with a comma and space in between the two.

___

##QUESTION #3 — Sort the inventors by birthdate, oldest to youngest

```js
  inventors.sort((a, b) => a.year > b.year ? 1 : -1)
```

___

##QUESTION #4 — How many years did all the inventors live?

```js
  const totalYears = inventors.reduce( (total, inventor) => {
    return total + (inventor.death - inventor.year);
  }, 0);
```

___

##QUESTION #5 — Sort the inventors by years lived

```js
const oldest = inventors.sort(function(a, b) {
  const lastGuy = a.passed - a.year;
  const nextGuy = b.passed - b.year;
  return lastGuy > nextGuy ? -1 : 1;
});

```

___

##QUESTION #6 — create a list of [Boulevards in Paris](https://en.wikipedia.org/wiki/Category:Boulevards_in_Paris) with 'de' in the name

```js
  const category = document.querySelector('.mw-category');
  const links = Array.from(category.querySelectorAll('a'));
  const de = links
    .map(link => link.textContent)
      .filter(streetName => streetName.includes('de'));
```

___

## QUESTION #7 — sort the names in the `people` array alphabetically

```js
  const alpha = people.sort((lastOne, nextOne) => {
    const [aLast, aFirst] = lastOne.split(', ');
    const [bLast, bFirst] = nextOne.split(', ');
    return aLast > bLast ? 1 : -1;
  });
```

___

## QUESTION #8 — Sum up the instances of each word in the `words` array

```js
  const tally = data.reduce((obj, item) => {
    if (!obj[item]) obj[item] = 0;
    obj[item]++;
    return obj;
  },{});
```


___


