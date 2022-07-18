<!--SuiGn notes on Javascript-->

Use this to split a string input givien in hackerrank

```js
  const rows = input.split('\n');
	 rows.shift() // skip operation count takes away first useless element
```



 *//Enter your code here*

  *//Repeat a string n numbers of times a.repeat(n);*

  *//Getting the specified character in a string string.charAt(0)*

  *//append string to end of string string.concat(string2);*

  *//Remove character at certain index mystring.replaceAt(4, '')*

  *//const withoutLast3 = str.slice(0, -3);*

  *//console.log(withoutLast3); // hello wo*

  */\*Passing an end index parameter of -3 and str.length - 3 is the same. We instruct the slice method to go up to, but not including the last 3 characters in the string.*

  **/*

### isNaN

**Function tries to convert the string into a number and if it fails, it returns `true`.**

The global **`NaN`** property is a value representing Not-A-Number.

**[Sintaxis]**

```Javascript
isNaN(valor)
```

### Check if Character in String is a Number with Regex

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

REGEX

```js
const str = 'apple, banana, corn, dates';
// 👇️ ['apple', ' banana', ' corn', ' dates']
console.log(str.split(','))
var array = str.split(/[ ,.]+/); //splits string using RegEx on a space, comma OR dot
array.split('').sort().join(''); // splits by character and then sorts them alphabetically.
```

### POP Method

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

###### Square Matrix diagonals:

The primary diagonal is formed by the elements A00, A11, A22, A33. 

1. Condition for Principal Diagonal: The row-column condition is row = column. 
   The secondary diagonal is formed by the elements A03, A12, A21, A30.

2. Condition for Secondary Diagonal: The row-column condition is row = numberOfRows – column -1.

   ```js
   array[i][n - i - 1] //condicion para formar la segunda diagonal de derecha a izquierda.
   ```

   ```js
   //Suma de Diagonales y obtener diferencia de la suma de las dos diagonales.
   let arr = [
       [11, 2, 4],
       [4, 5, 6],
       [10, 8, -12]
   ];
   
   function sumDiagonals(x){
       let diagonal = 0;
       let secondDiagonal = 0;
       for(let i = 0; i < x.length; i ++){
          diagonal += x[i][i];
          secondDiagonal += arr[i][x.length - i - 1];
       }
       let result = Math.abs(diagonal - secondDiagonal);
       console.log(result);
   }
   
   sumDiagonals(arr);
   
   //same but leetcode
   function diagonalDifference(arr) {
       // Write your code here
       var diagonal = 0;
       var secondDiagonal = 0;
     for (let i = 0; i < arr.length; i++){
         diagonal += arr[i][i];
         secondDiagonal += arr[i][arr.length - i -1];
     }
     let result = Math.abs(diagonal - secondDiagonal);
     return result;
   }
   ```

### Maths.abs()

Math.*abs*() retorna el valor absoluto de un número

#### Javascript to LowerCase

```js
let text = "Hello World!";
 let result = text.toLowerCase();
```

#### GETTING THE SPECIFiED CHARACTER IN A STRING

```js
//Syntax:
//STRING.charAt(INDEX)

//example
logs[log].charAt(0)
var logs = ["dig1 8 1 5 1","let1 art can","dig2 3 6","let2 own kit dig","let3 art zero"];
var reorderLogFiles = function(logs) {
    const letters = []
    const digits = []
    
    for (log in logs){
        console.log(logs[log].charAt(0)); // d, l, d, l, l
    }
};
reorderLogFiles(logs);
```

#### Repeat a String N number of times:

```js
"a".repeat(10);
Array(11).join("a") // create string with 10 a's: "aaaaaaaaaa"
```

#### Suma de valores en un array:

```js
var arr = [1, 2, 3, 4];
var total = 0;
for (var i in arr) {
  total += arr[i];
}
```

#### Add Strings as Numbers in JavaScript

```js
const str1 = '5';
const str2 = '15';

const result = Number(str1) + Number(str2);
console.log(result); // 👉️ 20

console.log(typeof result); // 👉️ number
```

#### Count characters in integer javascript

```js
var length = (number + '').replace('.', '').replace('-', '').length; 
```

### Adding elements to a JS Queue.

```js
function processData(input) {
    //Enter your code here
    let data = input.split("\n"); //split data by newlines, makes array.
   let queue = [];
    for (let i=1; i < data.length; i++){
        let arg = data[i].split(' '); //split data
        if (arg[0] == 1)
                queue.push(arg[1]); //pushes first element
        else if (arg[0] == 2)
                queue.shift(); //removes first element in queue
        else if (arg[0] == 3)
                console.log(queue[0]); //print first element
    }
} 
```

### Check if string of brackets is balanced or unbalanced:

https://www.hackerrank.com/challenges/one-week-preparation-kit-balanced-brackets/forum?isFullScreen=true&h_l=interview&playlist_slugs%5B%5D=preparation-kits&playlist_slugs%5B%5D=one-week-preparation-kit&playlist_slugs%5B%5D=one-week-day-five

```js
function isBalanced(s) {
    // Write your code here
   let open = ['{', '(', '[']
    let close = ['}', ')', ']']
    
    let t = [] // stack
    for (const c of s) {
        if (open.includes(c)) t.push(c)
        else if (t[t.length - 1] === open[close.indexOf(c)]) {
            if (t.length === 0) return 'NO' 
            t.pop()
        } else return 'NO'
    }
    if (t.length) return 'NO'
    return 'YES'

}
```

### Split a string into rows divided by a space and compute each row to follow instructions

Implement a simple text editor. The editor initially contains an empty string, . Perform  operations of the following 

 types:  

![Screen Shot 2022-04-04 at 20.49.40](/Users/suign/Library/Application Support/typora-user-images/Screen Shot 2022-04-04 at 20.49.40.png)

```js
function processData(input) {
    const undo = [] // undo stack storing previous string (alternative is to store the ops)
    const rows = input.split('\n')
    rows.shift() // skip operation count
    let s = '' // initial string
    for (r of rows) {
        let [op, arg] = r.split(' ')
        switch (op) {
            case '1':
                undo.push(s)
                s = s + arg
                break
            case '2':
                undo.push(s)
                s = s.slice(0, -+arg)
                break
            case '3':
                console.log(s[+arg - 1])
                break
            case '4':
                s = undo.pop()
                break
        }
    }
}
```

## Removing Array Items By Value Using Splice

If you know the  value you want to remove from an array you can use the splice method.  First you must identify the index of the target item. You then use the  index as the start element and remove just one element.

```javascript
    var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0];
    for( var i = 0; i < arr.length; i++){ 
        if ( arr[i] === 5) { 
            arr.splice(i, 1); 
        }    
    }
    //=> [1, 2, 3, 4, 6, 7, 8, 9, 0]
```

Instead I created an Array remove utility method that can be added to a helper or utility library. Like the Lodash remove method the first  parameter is the target array. It uses Array.filter to return elements  not matching a value.

```javascript
    function arrayRemove(arr, value) { 
        return arr.filter(function(ele){ 
            return ele != value; 
        });
    }
    
    var result = arrayRemove(array, 6);
    // result = [1, 2, 3, 4, 5, 7, 8, 9, 0]
```

