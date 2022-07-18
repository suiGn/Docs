## How do you sort numbers from least to greatest in JavaScript?

**“sort array highest to lowest javascript” Code Answer's**

1. ```js
   let numbers = [5, 13, 1, 44, 32, 15, 500]
   let lowestToHighest = numbers. sort((a, b) => a - b);
   let highestToLowest = numbers. sort((a, b) => b-a);
   ```

   

## Filter Method:

```js
  var A = [5, 6, 7];

var k = 6;
function cookies(k, A) {
var B = A.filter(number => number < k);
console.log(B);
 }

cookies(k, A);
```



## Cookies problem:

```js
let i = 0,    // "Pointer" for A to avoid the need to shift
    j = 0,      // "Pointer" for C to avoid the need to shift
    n = 0,      // Number of operations
    a, b, res,  // Aux
    C = []      // Array with the calculated values

  // Sort the inicial array
  A.sort((a, b) => a - b)

  // Some shortcuts to speedup the edges
  if (A[0] >= k) return 0
  if (A.length < 2) return -1

  // Iterate while there are values in one of the arrays
  // C.lenght-1 has to do with the formula C[j] + 2 * C[j + 1]
  while (i < A.length || j < C.length - 1) {

    // In case A is empty, use only C
    if (i >= A.length) {
      res = C[j] + 2 * C[j + 1]
      j += 2  // Same effect of shift() twice, but less expensive
    } else {

      // Take the min between the two arrays
      // j >= C.length avoids error in the first run, where C is empty
      if (A[i] < C[j] || j >= C.length) {
        a = A[i]
        i++
      } else {
        a = C[j]
        j++
      }

      // Take the second smallest value
      // j >= C.length avoids error when there is no C[j] (remember previous j++)
      if (A[i] < C[j] || j >= C.length) {
        b = A[i]
        i++
      } else {
        b = C[j]
        j++
      }

      res = a + 2 * b
    }

    C.push(res) // Push the new calculated value
    n++         // Increment count

    // Finish when the min value of both stacks are >= k
    // or A is empty (i >= A.length) and min C >=k
    if ((A[i] >= k || i >= A.length) && C[j] >= k) return n

  }

  // If the last number isn't enough, then it's not possible
  return -1
```



## Return how many times the highest integer in the array is repeated.

```js
let arr = [18, 90, 90, 13, 90, 75, 90, 8, 90, 43];

function birthdayCakeCandles(candles) {
    // Write your code here
    var count = 1;
var max = candles[0];
    for (let i = 0; i < candles.length; i++){
        if(candles[i] > max){
            max = candles[i];
            count = 1;
        }else if (candles[i] == max){
            count++;
        }else{
            continue;
        }
    }
    console.log(count);
    console.log(max);

}

birthdayCakeCandles(arr);
```



## Javascript Recursive with Comments:

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @return {boolean}
 */
const isValidBST = function(root) {    
    function walkTree(node, min, max) {
        if (node === null) { // traversed entire tree without false return
            return true;
        }
        // check if mins and max exist and they are being violated
        if (min !== null && max !== null && (node.val <= min || node.val >= max)) {
            return false;
        }
        // continue checking nodes updating min and max
        // infinities are for values that arent set 
        // left node should be less than parent node and more than nothing 
        // right node should be greater than parent node and less than nothing
        // but once we go left and then right etc we will need to refer to the mins and maxes 
        return (
            walkTree(node.left, min || Number.NEGATIVE_INFINITY, node.val) &&
            walkTree(node.right, node.val, max || Number.POSITIVE_INFINITY)
        );
    }
    return walkTree(root, null, null);
};


// Other example

var isValidBST = function(root) {
    
   let validity = true;
    
    function helperDfs(node, min, max) {
        if (!node) return;
        
        if(
            (min !== null && (node.val > min) === false) || 
            (max !== null && (node.val < max) === false)) {
            validity = false;
            return;
        };
        
     
        helperDfs(node.left, min, node.val);
        helperDfs(node.right, node.val, max);
    }
    
    helperDfs(root, null, null);
    
    return validity;
    
};

```

### Big conditional with is not a number, is uppercase or match a string.

```js
if(dcr[i] === dcr[i].toUpperCase() && isNaN(parseInt(dcr[i])) && dcr[i].match(/[a-z]/i))
```

