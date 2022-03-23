## Commonly asked Array interview questions

- Most Common Word:

  Given a string paragraph and a string array of the banned words banned, return *the most frequent word that is not banned*. It is **guaranteed** there is **at least one word** that is not banned, and that the answer is **unique**.

  The words in paragraph are **case-insensitive** and the answer should be returned in **lowercase**.

  ```js
  var mostCommonWord = function(paragraph, banned) {
      let result = '';
      let wordObject = {};
      let repeated = 0
      
      paragraph = paragraph.toLowerCase().split(/\W+/); 
    
      for(let i = 0; i < paragraph.length; i++){
          var ind = paragraph[i];
          if(!banned.includes(ind)){
              wordObject[ind] = wordObject[ind] + 1 || 1;
          }
      }
      
      for(let word in wordObject){
          if(wordObject[word] > repeated){
              console.log(wordObject)
              repeated = wordObject[word];
              result = word
          }
      }
     
      return result
  
  };
  ```

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

  ```js
  //Merge two sorted Arrays
  const points = [40, 100, 1, 5, 25, 10];
  const points2 =[35, 25, 52, 67, 234, 7]; 
  var newArray = [].concat(points, points2).sort(function(a, b){return a-b});
  
  console.log(newArray);
  ```

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