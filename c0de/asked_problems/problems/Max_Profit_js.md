## Max Profit

https://algo.monster/problems/amazon_oa_max_profit

An Amazon seller is deciding which of their products to invest in for the next quarter to maximize their profits. They have each of their products listed as segments of a circle. Due to varying market conditions, the products do not sell consistently. The seller wants to achieve maximum profit using limited resources for investment. The product list is segmented into a number of equal segments, and a projected profit is calculated for each segment. The projected profit is the cost to invest versus the sale price of the product. The seller has chosen to invest in a number of contiguous segments along with those opposite. Determine the maximum profit the seller can achieve using this approach.

![Amazon OA Max Profit](https://algomonster.s3.us-east-2.amazonaws.com/amazon_oa_max_profit/max-profit.png)

For example, the product list Is divided into n = 6 sections and will select k = 2 contiguous sections and those opposite to invest in. The profit estimates are `profit = [1, 5, 1, 3, 7, -3]` respectively. The diagrams below show the possible choices with `profits[0]` at the 9 o'clock position and filling counterclockwise.

https://leetcode.com/discuss/interview-question/1321204/efficient-harvest-faang-oa-question-2021

```js
var length = profit.length;
    var half_length = length / 2;
    var max = 0;
    //get the profit for index 0;
    for (var i = 0; i < k; i ++) {
        max += profit[i];
        max += profit[(i+half_length) % length];
    } 
        
    var current_profit = max;
    for (var i = 1; i < length/2; i ++) {
        current_profit -= profit[i - 1];
        current_profit -= profit[(i - 1 + half_length) % length]
        
        current_profit += profit[i + k - 1]
        current_profit += profit[(i + k - 1 + half_length) % length]
        max = Math.max(max, current_profit);
    }
    
    return max;
```

