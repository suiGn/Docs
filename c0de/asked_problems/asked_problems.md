## Commonly asked Array interview questions

<!-- SuiGn notes. -->

### Most Common Word:

Given a string paragraph and a string array of the banned words banned, return *the most frequent word that is not banned*. It is **guaranteed** there is **at least one word** that is not banned, and that the answer is **unique**.

The words in the paragraph are **case-insensitive** and the answer should be returned in **lowercase**.

```js
var paragraph = "I have been waiting been for you all of my life and you have been running away always";
var banned = [];
let repeated = 0;
function mostCommonWord(paragraph, banned){
   var text = paragraph.toLowerCase().split(/\W+/); 
    var words = [];
for( let i = 0; i < text.length; i++){
    if(!banned.includes(text[i]) ){
        words[text[i]] = words[text[i]] + 1 || 1;
    }
}
for (word in words){
  if(words[word] > repeated){
      repeated = words[word];
      result = word;
  }
}
console.log(result, repeated, words);
}
mostCommonWord(paragraph, banned);
```

### Find the second minimum element of an array:

```js
//Find the second smallest number in an array:

n = [3, 10, 5, 7, 20, 6, 8, 1, 4];
var first = Number.MAX_VALUE; //set to maximum value
var second = Number.MAX_VALUE ; //set to maximum value

for(i = 0; i < n.length; i ++){ //loop through the whole array
	if(n[i] < first){ //If current value in array is smaller than first current value
		second = first; //set second as first, because now this value is second
		first = n[i]; //set first to the new value found that is smaller.
	}else if (n[i] < second && n[i] != first){ //else if value is not smaller than first but smaller than second and it is different to first
		second = n[i]; //set second to new value found
	}
}

console.log("Looping through the array onle once.");
console.log("first:", first);
console.log("second:". second);

//Sorting the Array from smaller to largest and getting the first two elements.
n.sort(function(a, b){return a-b});
console.log("Sorting from smaller to largets and getting the first two elements.");
console.log("first:", n[0])
console.log("second:", n[1]);
```

### First non-repeating integers in an array

```js
const points = [40, 100, 1, 5, 25, 10, 100, 1, 25, 10, 40];
for (let i = 0; i < points.length; i++) {
  let j;
    for (j = 0; j < points.length; j++)
        if (i != j && points[i] == points[j])
            break;
    if (j == points.length)
        var nonRepeat = points[i];
}
console.log(nonRepeat);
```



### Caesars Cipher

- Julius Caesar protected his confidential information by encrypting it using a cipher. [Caesar's cipher](https://en.wikipedia.org/wiki/Caesar_cipher) shifts each letter by a number of letters.  If the shift takes you past the end of the alphabet, just rotate back to the front of the alphabet.  In the case of a rotation by 3, w, x, y and z would map to z, a, b and c.

  ```
  Original alphabet:      abcdefghijklmnopqrstuvwxyz
  Alphabet rotated +3:    defghijklmnopqrstuvwxyzabc
  ```

  **Example** 

  
  The alphabet is rotated by , matching the mapping above.  The encrypted string is 

  .  

  **Note:** The cipher *only* encrypts letters; symbols, such as `-`, remain unencrypted.  

  **Function Description**  

  Complete the *caesarCipher* function in the editor below.  

  caesarCipher has the following parameter(s):

  - *string s*: cleartext  
  - *int k*: the alphabet rotation factor  

  **Returns**  

  - *string:*  the encrypted string  

```javascript
function caesarCipher(s, k) {
    // Write your code here
var s = "www.abc.xy";
var k = 87;
      if( k>25 ){
    k=k%26
}; 
let abc = "abcdefghijklmnopqrstuvwxyz"
let ABC = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
let subS = abc.substring(k, abc.length) +
abc.substring(0, k);
let SUBS = ABC.substring(k, ABC.length) +
ABC.substring(0, k);
let cypher = "";

for (let i = 0 ; i < s.length; i ++){
    //console.log(s[i]);
    if(abc.includes(s[i])){
    let index = abc.indexOf(s[i]);
   cypher = cypher + subS[index];
    }else if(ABC.includes(s[i])){
        let IN = ABC.indexOf(s[i]);
        cypher = cypher + SUBS[IN];
    }else{
        cypher = cypher + s[i];
    }
} 
return cypher;
}
```

### Merge two sorted arrays

```js
//Merge two sorted Arrays
const points = [40, 100, 1, 5, 25, 10];
const points2 =[35, 25, 52, 67, 234, 7]; 
var newArray = [].concat(points, points2).sort(function(a, b){return a-b});

console.log(newArray);
```

### Rearrange positive and negative values in an array

```js
var digits = [-2, -20, 8, -5, 1 , 5, -6, 5, 3, -1];
var negatives = [];
var positives = [];
for(let digit of digits){

if(digit < 0){
negatives.push(digit);
}else{
positives.push(digit);
}
}
digits.sort((a,b) => a-b); //smallest to biggest
//console.log(negatives.sort((a,b) => a - b));
//console.log(positives.sort());
console.log(digits);
```

### Longest non repeating character Substring inside a string.

```js
var s = "aebeqwertyuiopasdfghjklñlkjhgfdsaqazwsxedcrfvtgbyhnghjkl";
var subS = new Set();
var j = 0;
var max = 0;
for (let i = 0; i < s.length; i ++){
   while(subS.has(s[i])){
       subS.delete(s[j]);
       j = j + 1;
   };
   subS.add(s[i]);
  max = Math.max(max, i - j + 1);
}
console.log(max);
```

### TWO SUM

Given an array of integers (array) and an integer (target) , return indices of the two numbers such that they add up to target.

​				****This is a Brute Force n2 solution*:**

```javascript
//Find two elements that summed together gives you the value of target. You can not repeat a value.

//This is a Brute Force n2 solution. It itinerates through all options.
  var array = [0, 5, 3, 6, 9, 10];
  var target = 8;

  var twoSummed = function(array, target){
  	//Loop through the array
  	for (let i = 0; i < array.length; i ++){
  		//for each itineration of i, loop through all the next elements with j
  		// j Plus 1 so we do not repeat array elements.
  		for (let j = i + 1; j < array.length; j ++){ 
  			//if condition of element i and element j in array is met
  			if ( array[i] + array[j] === target){
  				//return answer
  				return [i, j];
  			}
  		} 
  	}
  };

//Same but cleaned.
var twoSum = function(nums, tar) {
    for (var i = 0; i < nums.length; i++) {
        for (var j = i + 1; j < nums.length; j++) {
         if (nums[i] + nums[j] === tar) {
           return [i, j];
      }      
}}
};
```

​				 **Faster Solution:**

```javascript
//FASTER SOLUTION. We can write a faster algorithm that will find pairs that sum to S in linear time. With the use of hash tables. As we pass through each element in the array, we check to see if S minus the current element exists in the hash table. We only need to loop through the array once, resulting in a running time of O(n) since each lookup and insertion in a hash table is O(1).
/*
(1) The hash table is initially empty. We store first element on hash table.

(2) Check next element. We check to see if the sum minus the current element exists in the hash table.  Add element to the hash table for future reference if condition not matched.

(3) Check next element. We check to see if the sum minus the current element exists in the hash table. Sum does exist in the hash table so we found a pair!
*/

//Two Sum 
var nums = [3, 5, 3, 7, 8, 9, 4, 3];
var target = 9;
var elements =[];

for (let i = 0; i < nums.length; i ++){
    var sum = target - nums[i];
    if(sum in elements){
        console.log(elements[sum], i);
    }
    elements[nums[i]] = i;
}


//for leetcode output format
var twoSum = function(nums, target) {
    const elements = {};
    for (let i = 0; i < nums.length; i++) {
        const sum = target - nums[i];
        if (sum in elements) {
            return [elements[sum], i]
        }
        elements[ nums[i] ] = i
    }
}

//my solution
var twoSum = function(nums, target) {
 var memory = [];

var memory = [];

for (let i = 0; i < nums.length; i++){
    var x = target - nums[i];
    if(memory.includes(x)){
        return [nums.indexOf(x), i];
    }
  memory.push(nums[i]);
}
}

```

### Reorder Log Files

You are given an array of `logs`. Each log is a space-delimited string of words, where the first word is the **identifier**.

There are two types of logs:

- **Letter-logs**: All words (except the identifier) consist of lowercase English letters.
- **Digit-logs**: All words (except the identifier) consist of digits.

Reorder these logs so that:

1. The **letter-logs** come before all **digit-logs**.
2. The **letter-logs** are sorted lexicographically by their contents. If their contents are the same, then sort them lexicographically by their identifiers.
3. The **digit-logs** maintain their relative ordering.

Return *the final order of the logs*.

```js
var logs = ["dig1 8 1 5 1","let1 art can","dig2 3 6","let2 own kit dig","let3 art zero"];
var words = [];
var digits = [];

for (let log of logs){
    if (isNaN(log[log.length - 1])){
        // it is letter
      words.push(log);
    }
    else digits.push(log)
}
 var stra = words[0].substring(words[0].indexOf(" ") + 1);
 words.sort((a,b) => {
    var stra = a.substring(a.indexOf(" ") + 1); //remove index
    var strb = b.substring(b.indexOf(" ") + 1); //remove index
    if(stra === strb){ //if string is the same
       return a.localeCompare(b); //compare and sort with index
    }else{
        return stra.localeCompare(strb); //if not the same sort with string alphabet
    }
 })   
console.log(words.concat(digits));


```

### Sort Integer Array:

```js
var digit = [1 , 5, 6, 5, 3, 1];
var descending = digit.sort((a,b) => b-a); //biggest to smallest
var ascending = digit(sort); //smallest to biggest
```

#### SQUARE GRID OF CHARACTERS

Given a Square Grid of Characters rearrange the elements of each row alphabetically, ascending, Determine if the columns are also in ascending alphabetical order, top to bottom. Return YES if columns are ordered.

```js
function gridChallenge(grid) {
  // Write your code here
  let colsOrdered = 'YES';
  for (let row in grid) {
 grid[row] = grid[row].split('').sort().join('');
   if(colsOrdered == 'NO' || row == 0) continue;
  for(let col in grid[row]) {
    if (grid[row][col] < grid[row - 1][col]) {
     colsOrdered = 'NO';
   }
  }
  }
  return colsOrdered;
}
```

Other solution:

```js
function gridChallenge(grid) {
    let cur = [];
    for (let i = 0; i < grid.length; i++){
        let text = grid[i].split("").sort();
        cur.push(text);
    }
    let column = cur[0].length;
    for (let j = 0; j < cur.length -1; j++){
        for (let z = 0; z < column; z++){
            if(cur[j][z] > cur[j + 1][z]){
                return "NO";
            }
        }
    }
    return "YES"
    }
```

#### Super Digits:

Find the one integer that is the sum of all the digits in an integer for example 

256 = 2 + 5 + 6 = 13 = 1 + 3 = 4 <-- 4 is the super digit.

```js
//NOT PASSING THE TEST WITH REALLY LONG NUMBERS.
function superDigit(n, k) {
    // Write your code here
    var numbers = [];
    var rNumber = n.repeat(k).split('');
    var total = 0;

    for (let i = 0; i < rNumber.length; i++){
    total = total + Number(rNumber[i]); 
   }

   while (total > 9){
    var reSuma = total.toString().split('').map(iNum => parseInt(iNum, 10)); 
    total = 0;
    for (let j = 0; j < reSuma.length; j++){
       total = total + reSuma[j];
        }
    }
console.log(total);
}


var n = "143";
var k = 3;

superDigit(n, k);

```

#### Truck Tour:

```js
 let petrol = 0;
    let pump = 0;

    for(let i = 0; i < petrolpumps.length; i++) {
        petrol += petrolpumps[i][0];
        petrol -= petrolpumps[i][1];
        if(petrol < 0) {
            petrol = 0;
            pump = i + 1;
        }
    }
    return pump
```

### Pairs

Find number of pairs in the array that the difference is equal to the target.

```js
function pairs(k, arr) {
    // Write your code here
    var count = 0;
    for (let i = 0; i < arr.length; i++){
       for (let j = i + 1; j < arr.length; j++){
           var difference = arr[i] - arr[j];
           if (Math.abs(difference) == k){
               count++
           }
       }
    }
    return count;
}
```

## PREFERRED QUALIFICATIONS

· Experience building complex software systems that have been successfully delivered to customers

###### Agile Scrum methodology is good for businesses that need to finish specific projects quickly:

- ### What are the values of agile?

  Agile was first described in the Agile Manifesto in 2000 by a group of developers who sought out a new method of writing software. The manifesto cites four values:

  1. Individuals and interactions over processes and tools
  2. Working software over comprehensive documentation
  3. Customer collaboration over contract negotiation
  4. Responding to change over following a plan

  ### What are the 12 principles of agile?

  The Agile Manifesto also enacted 12 principles in reference to software development and was later reconfigured to fit a wider perspective of users:

  1. Customer satisfaction
  2. Early and continuous delivery
  3. Embrace change
  4. Frequent delivery
  5. Collaboration of businesses and developers
  6. Motivated individuals
  7. Face-to-face conversation
  8. Functional products
  9. Technical excellence
  10. Simplicity
  11. Self-organized teams
  12. Regulation, reflection and adjustment

###### -----------------------------------------------------------------------------------

· Knowledge of professional software engineering practices & best practices for the full software development life cycle, including coding standards, code reviews, source control management, build processes, testing, and operations.

###### -----------------------------------------------------------------------------------

· Ability to take a project from scoping requirements through actual launch of the project.

###### -----------------------------------------------------------------------------------

· Experience in communicating with users, other technical teams, and management to collect requirements, describe software product features, and technical designs.

###### -----------------------------------------------------------------------------------

· Experience developing data privacy solutions, including data handling techniques (e.g. pseudonymization, anonymization, data scrubbing)







