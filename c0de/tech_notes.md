# Data Structures:

<!--SuiGn notes on Javascript-->

It is the way we organize data that enables us to handle it efficiently for access and modification.

Organize data so that needed operations run fast.

What functions and operations can be applied to certain **data structures.**

Data structures are layouts of data. The goal is to pick the best data structure for a problem as the way it is stored makes it efficiently for some purposes and inefficient for others.

**Commonly used data structures:**

- Arrays

- Hash Tables

- Stacks

- Queus

- Linked Lists

- Trees

- Graphs

- Tries

  

## Arrays:

Data elements are assigned a positive numerical value (almost always starting with 0), this is called an index. The index is the number of the box that contains a piece of data in the array.

**Basic Arrays Operations:**

**Insert -** Adds an element to the array, it could be assigned to whatever place you need.

**Get -** Returns the element of a given index.

**Delete -** removes an element of the array given an index or a condition to match.

**Size -** Gets the total number of elements in the array.

*Methods to Search for an item or items in an array:*

1. Filter: find all items in an array that meets a specific condition.

2. Find: find the first item that meets a condition.

3. Includes: check if an array contains an given value.

4. IndexOf: find the index of a particular item in an array.

   

###### <u>Filter Method:</u>

**array.filter()** -> **find all elements in an array** that meet a certain condition.

E.g -> Get all elements in an array of numbers that are greater than 5.

**Syntax:**

```javascript
/*
Where:
newArray - the new array that will store the filtered result.
array - the array we are applying the filter too.
callback - a function that is applied to each element of the array.
*/
let newArray = array.filter(callback);
```

**Example of usage:**

```javascript
var array = [0, 2, 11, 3, 1, 15];
var greaterThanFive = array.filter(element => element > 5);
console.log(greaterThanFive); // 11, 15
```

According to MDN documentation:

The filter method creates a new array with all elements that pass the test implemented by the provided function.

The callback function takes 3 arguments:

1. Element: the current element in the array being processed.
2. Index: The index of the current element.
3. Array: The array the filter was applied too.

The filter method returns a new array. It does not changes the original array the filter was applied too.

<u>*When to use the Filter Method?*</u>

**When you want only items that meet a required condition in an array.**



###### <u>Find Method</u>:

Used to **find the first element that meets a certain condition.**

Takes a callback as an argument and returns the first element that matched the condition.

**Syntax:**

```javascript
/*
Where:
newArray - the new array that will store the filtered result.
array - the array we are applying the filter too.
callback - a function that is applied to each element of the array.
*/
let newArray = array.find(callback);
```

**Example of usage:**

```javascript
var array = [0, 2, 11, 3, 1, 15];
var greaterThanFive = array.find(element => element > 5);
console.log(greaterThanFive); // 11
```

Takes three arguments:

1. Element: required.
2. Index: Optional.
3. Array: Optional.

If no condition is met it returns undefined.



###### <u>Includes Method</u>:

Determines if a certain value exists in the array and returns True or False accordingly.

**Syntax:**

```javascript
/*
Where:
includesValue = Boolean according if element exists or not
findValue - the value to check if exists. (required)
fromIndex - specify from what position to start looking. (optional)
*/
let includesValue = array.find(findValue, fromIndex);
```

**Example of usage:**

```javascript
//array we are going to check
var array = [0, 2, 11, 3, 1, 15];
//find if 5 is contained on the array
var fiveIncluded = array.includes(5);
console.log(fiveIncluded); // False
```

This method accepts a value as the argument we want to find if its included in the array.



###### <u>indexOf Method</u>:

Returns the index at which an element is first found on an array.

**Syntax:**

```javascript
/*
Where:
element - the value to check (required).
fromIndex - specify from what position to start looking. (optional)
*/
let indexOfElement = array.indexOf(element, fromIndex);
```

**Example of usage:**

```javascript
//array we are going to check
var array = [5,0, 2, 11, 5, 3, 1, 15];
//find where is 5 located in the array.
var indexOfFive = array.indexOf(5);
console.log(indexOfFive); // 0

//Using both arguments element (required) and fromIndex (optional) to skip the first 5.
var array = [5,0, 2, 11, 5, 3, 1, 15];
//find where is the first 5 located in the array after skiping the first element.
var indexOfFive = array.indexOf(5, 1);
console.log(indexOfFive); // 4
```

This method accepts a value as the argument we want to find the indexOf.

Both `indexOf` and `includes` methods use strict equality **( '===' )** to search an array. If the values are of different types (for example '7' and 7), they'll return `false` and `-1` respectively.



## Commonly asked Array interview questions

- Find the second minimum element of an array:

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

  

- First non-repeating integers in an array

```javascript

```

- Merge two sorted arrays

- Rearrange positive and negative values in an array

- Given an array of integers (array) and an integer (target) , return indices of the two numbers such that they add up to target.

  ​				**This is a Brute Force n2 solution*:

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
  
  var twoSum = function(array, target) {
      const indices = {};
      for (let index = 0; index < nums.length; index++) {
          const complement = target - nums[index];
          if (complement in indices) {
              return [indices[complement], index]
          }
          indices[ nums[index] ] = index
      }
  }
  
  ```

  Given an array of integers (array) and an integer (target) , return indices of the two numbers such that they add up to target.

## Hash Tables



#### Commonly asked Hashing interview questions

- Find symmetric pairs in an array
- Trace complete path of a journey
- Find if an array is a subset of another array
- Check if given arrays are disjoint











