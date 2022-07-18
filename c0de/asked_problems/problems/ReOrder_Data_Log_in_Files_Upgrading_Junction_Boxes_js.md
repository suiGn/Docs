## Reorder Data in Log Files | Upgrading Junction Boxes | HackerRank

937. Reorder Data in Log Files:  https://leetcode.com/problems/reorder-data-in-log-files/

You are given an array of `logs`. Each log is a space-delimited string of words, where the first word is the **identifier**.

There are two types of logs:

- **Letter-logs**: All words (except the identifier) consist of lowercase English letters.
- **Digit-logs**: All words (except the identifier) consist of digits.

Reorder these logs so that:

1. The **letter-logs** come before all **digit-logs**.
2. The **letter-logs** are sorted lexicographically by their contents. If their contents are the same, then sort them lexicographically by their identifiers.
3. The **digit-logs** maintain their relative ordering.

Return *the final order of the logs*.

var reorderLogFiles = function(logs) {
    const letters = []
    const digits = []
    

```js
var reorderLogFiles = function(logs) {
    const letters = []
    const digits = []
    
for (let log of logs){

    if (isNaN(log[log.length - 1])){
        // it is letter
        letters.push(log)
    }
    else digits.push(log)
}

letters.sort((a,b)=> {
        stra = a.substr(a.indexOf(' ') + 1)
        strb = b.substr(b.indexOf(" ") + 1)
        
        if (stra == strb) return a.localeCompare(b) 
        else return stra.localeCompare(strb)            
})
return letters.concat(digits)
};
```

## 