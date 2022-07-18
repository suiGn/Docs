##  Optimal Utilization

Amazon | OA 2019 | Optimal Utilization: https://leetcode.com/discuss/interview-question/373202/amazon-oa-2019-optimal-utilization

Given 2 lists `a` and `b`. Each element is a pair of integers where the first integer represents the unique id and the second integer represents a value. Your task is to find an element from `a` and an element form `b` such that the sum of their values is less or equal to `target` and as close to `target` as possible. Return a list of ids of selected elements. If no pair is possible, return an empty list

```js
function getPairs(A, B, target) {
  A.sort((a, b) => a[1] - b[1]);
  B.sort((a, b) => a[1] - b[1]);

  let res = [];
  let max = -Infinity;
  let l = 0;
  let r = B.length - 1;

  while (l < A.length && r >= 0) {
    let sum = A[l][1] + B[r][1];
    if (sum > target) {
      r--;
    } else {
      if (max <= sum) {
        if (max < sum) {
          max = sum;
          res = [];
        }
        res.push([A[l][0], B[r][0]]);
        let i = r - 1;
        while (i >= 0 && B[i][1] === B[i + 1][1]) {
          res.push([A[l][0], B[i][0]]);
          i--;
        }
      }
      l++;
    }
  }
  return res;
}

console.log(getPairs([[1, 8], [2, 7], [3, 14]], [[1, 5], [2, 10], [3, 14]], 20));
console.log(getPairs([[1, 8], [2, 15], [3, 9]], [[1, 8], [2, 11], [3, 12]], 20));


```

