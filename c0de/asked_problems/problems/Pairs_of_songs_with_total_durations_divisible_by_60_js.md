##  Pairs of Songs With Total Durations Divisible by 60

Amazon Online Assessment (OA) 

### Explanation

This question is basically Two Sum with modulo. If you are unfamiliar with the modulo operator, check out [this article](https://www.khanacademy.org/computing/computer-science/cryptography/modarithmetic/a/what-is-modular-arithmetic). Essentially, we convert every number to its modulo 60 and then do Two sum.

1010. Pairs of Songs With Total Durations Divisible by 60

You are given a list of songs where the `ith` song has a duration of `time[i]` seconds.

Return *the number of pairs of songs for which their total duration in seconds is divisible by* `60`. Formally, we want the number of indices `i`, `j` such that `i < j` with `(time[i] + time[j]) % 60 == 0`.

```js
var numPairsDivisibleBy60 = function(time) {
  const container = Array(60).fill(0);
  let count = 0;
  for (const t of time) {
    const mod = t % 60; 
    const left = (60 - mod) % 60; 
    count += container[left];
    container[mod]++;   
  }
  return count;
};
```

