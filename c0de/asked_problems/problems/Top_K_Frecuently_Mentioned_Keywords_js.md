## Top K Frequently Mentioned Keywords | SHL

692. Top K Frequent Words: https://leetcode.com/problems/top-k-frequent-words/

Given an array of strings `words` and an integer `k`, return *the* `k` *most frequent strings*.

Return the answer **sorted** by **the frequency** from highest to lowest. Sort the words with the same frequency by their **lexicographical order**.

**Example 1:**

```
Input: words = ["i","love","leetcode","i","love","coding"], k = 2
Output: ["i","love"]
Explanation: "i" and "love" are the two most frequent words.
Note that "i" comes before "love" due to a lower alphabetical order.
```

```js
  var topKFrequent = function(words, k) {
      const map = {};
  
  for (let i=0; i < words.length; i++) {
    map[words[i]] = map[words[i]] ? map[words[i]] + 1 : 1;
  }
  
  const table = Object.entries(map);
  table.sort((a, b) => b[1] - a[1] || (b[0] < a[0] ? 1 : -1));
  return table.slice(0, k).map(([word]) => word);

};




//other solution
var topKFrequent = function(nums, k) {
    // object to store frequency of a number in nums
    let map = {};
    // storing frequency in nums using for loop
    for(let i of nums) map[i] ? map[i]++ : map[i] = 1;
    // sorting keys in decreasing order using their values and 
	// slice to return the required array
    return Object.keys(map).sort((a,b) => map[b] - map[a]).slice(0, k);
};
```

