## Add items to an Array with push() and unshift() method:

Arrays lenghts and data it contained is not fixed.

**.push()** adds elements to the end of an array

**.unshift()**  adds elements to the beginning.

Example:

```js
let twentyThree = "XXIII";
let romanNumerals = ["XXI", "XXII"];

romanNumerals.unshift("XIX", "XX");
//[ 'XIX', 'XX', 'XXI', 'XXII' ]

romanNumerals.push(twentyThree);
//[ 'XIX', 'XX', 'XXI', 'XXII', 'XXIII' ]
```

We can pass one or more parameters to both methods. We could also pass variables.

