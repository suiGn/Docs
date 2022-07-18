## Count Binary Substrings

696. Count Binary Substrings: https://leetcode.com/problems/count-binary-substrings/

Kindle Direct Publishing, Amazons e-book self publishing platform, is working on a new feature to help authors track the use of text strings in different ways. A substring is a group of contiguous characters in a string. For instance, all substring of abc are [a, b, c, ab, bc ,abc].

Given a binary representation of a number, determine the total number of substring present that match the following conditions:

Give a binary string `s`, return the number of non-empty substrings that have the same number of `0`'s and `1`'s, and all the `0`'s and all the `1`'s in these substrings are grouped consecutively.

Substrings that occur multiple times are counted the number of times they occur.

(THIS IS A TWO POINTER PROBLE)

```JS
var countBinarySubstrings = function(s) {
    s += '#';
    let curr = 1, prev = 0, count = 0;
    
    for(let i = 1; i < s.length; i++) {
        if(s[i-1] === s[i]) curr++;
        else {
            count += Math.min(prev, curr);
            prev = curr;
            curr = 1;
        }
    }
    return count;
};
```

