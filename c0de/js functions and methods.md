<!--SuiGn notes on Javascript-->





## isNaN

**Function tries to convert the string into a number and if it fails, it returns `true`.**

The global **`NaN`** property is a value representing Not-A-Number.



## [Sintaxis]

```Javascript
isNaN(valor)
```

## Check if Character in String is a Number with Regex

```javascript
function isNumber(char) {
  return /^\d$/.test(char);
}
```

Parse String to Integer

```javascript
var x = parseInt(stringValueX, 10);  
```

## JavaScript For Loop

Execute a block of code a number of times.

Syntax:

```Javascript
for (let i = 0; i < cars.length; i++) {
 text += cars[i] + "<br>";
}
```

Different  loops:

[Site: w3 schools]: (https://www.w3schools.com/js/js_loop_for.asp):

- `for` - loops through a block of code a number of times
- `for/in` - loops through the properties of an object
- `for/of` - loops through the values of an iterable object
- `while` - loops through a block of code while a specified condition is true
- `do/while` - also loops through a block of code while a specified condition is true



## The For Loop

The `for` loop has the following syntax:

```javascript
for (*statement 1*; *statement 2*; *statement 3*) {
 // *code block to be executed*
}
```

## The While Loop

The `while` loop loops through a block of code as long as a specified condition is true.

### Syntax

```javascript
while (*condition*) {
 *// code block to be executed*
}
```

### Example

```javascript
while (i < 10) {
 text += "The number is " + i;
 i++;
}
```



###### Get the smalles Number in an array:

Imagine you have this array:

```js
var arr = [1, 2, 3];
```

ES6 way:

```js
var min = Math.min(...arr); //min=1
```

# JavaScript Array sort()



The `sort()` sorts the elements of an array.

The `sort()` overwrites the original array.

The `sort()` sorts the elements as strings in alphabetical and ascending order.



**Sort Compare Function**

Sorting alphabetically works well for strings ("Apple" comes before "Banana").

But, sorting numbers can produce incorrect results.

"25" is bigger than "100", because "2" is bigger than "1".

You can fix this by providing a "compare function" (See examples below).

Sort numbers in ascending order:

```js
const points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){return a-b});
```



###### The `split` method returns an array containing the split strings.

```javascript
const str = 'apple, banana, corn, dates';
// 👇️ ['apple', ' banana', ' corn', ' dates']
console.log(str.split(','))
var array = str.split(/[ ,.]+/); //splits string using RegEx on a space, comma OR dot
```

The pop method removes the last element of the array, returns that element, and updates the length property. The pop method modifies the array on which it is invoked, This means unlike using delete the last element is removed completely and the array length reduced.

```javascript
    var ar = [1, 2, 3, 4, 5, 6];
    
    ar.pop(); // returns 6
    
    console.log( ar ); // [1, 2, 3, 4, 5]
```

###### Merge two arrays:

`**[].concat(array1, array2)**`



###### SET

Set objects are collections of values that can only be store once.

elements of the set can be iterated in the insertion order. Set can store any types of values whether primitive or objects.
**Syntax:** 

`new Set([it]);`

**Parameter:** 
**it** - It is an iterable object whose all elements are 
added to the new set created, 
If the parameter is not specified or null is passed 
then a new set created is empty.

Returns:
A new set object

Now lets create some sets: 
**Example:** 

```js
var set1 = new Set(["sumit","sumit","amit","anil","anish"]); // ["sumit","amit","anil","anish"]
console.log(set1);
var set2 = new Set("fooooooood");
console.log(set2);// it contains 'f', 'o', 'd'
var set3 = new Set([10, 20, 30, 30, 40, 40]);// it contains [10, 20, 30, 40]
console.log(set3); // it is an  empty set
var set4 = new Set();
console.log(set4); // empty
```

###### Set.prototype.has()

El método `**has()**` retorna un booleano indicando si el elemento especificado existe en el objeto `Set` o no.

###### [Syntaxis](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Set/has#syntaxis)

```js
mySet.has(value);
```

