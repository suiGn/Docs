##  Storage Optimization | HackerRank

Amazon Online Assessment (OA) 2021 

```javascript
/ returns length of the longest consecutive subsequence
function longest(arr) {
    arr.sort();
    let last = -1;
    let consec = 0;
    let maxConsec = 0;
    for (const val of arr) {
        if (val != last + 1)
            consec = 0;
        last = val;
        consec++;
        maxConsec = Math.max(maxConsec, consec);
    }
    return maxConsec;
}

function storageOptimization(n, m, h, v) {
    return (longest(h) + 1) * (longest(v) + 1);
}

```

