## Minimum Difficulty of a Job Schedule

1335. Minimum Difficulty of a Job Schedule : https://leetcode.com/problems/minimum-difficulty-of-a-job-schedule/

You want to schedule a list of jobs in `d` days. Jobs are dependent (i.e To work on the `ith` job, you have to finish all the jobs `j` where `0 <= j < i`).

You have to finish **at least** one task every day. The difficulty of a job schedule is the sum of difficulties of each day of the `d` days. The difficulty of a day is the maximum difficulty of a job done on that day.

You are given an integer array `jobDifficulty` and an integer `d`. The difficulty of the `ith` job is `jobDifficulty[i]`.

Return *the minimum difficulty of a job schedule*. If you cannot find a schedule for the jobs return `-1`.

```js
var minDifficulty = function(A, d) {
     const L = A.length;
  const dp = Array.from(Array(d), () => Array(L));
  for (let i = 0; i < d; i++) {
    for (let j = 0; j < L; j++) {
      if (i === 0) dp[i][j] = Math.max(j >= 1 ? dp[i][j - 1] : 0, A[j]); 
      else if (i > j) dp[i][j] = -1; 
      else {
        let max = A[j];
        for (let k = 1; k <= j && i - 1 <= j - k; k++) {
          max = Math.max(max, A[j - k + 1]);
          dp[i][j] = Math.min(dp[i][j] || Infinity, dp[i - 1][j - k] + max);
        }
      }
    }
  }

  return dp[d - 1][L - 1];
};


```

