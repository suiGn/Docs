## Shipment Imbalance

https://leetcode.com/problems/sum-of-subarray-ranges/

Amazon logistics has multiple delivery centers from which products are sent.

In one such delivery center, parcels are placed in a sequence where the i-th parcel  has a weight of weigth[i]. A shipment is constituted of a contigous segment of parcels. The shipment imbalance of a shipment is defined as the difference between the max and min weights within a shipment.

Given the arrangement of parcers, find the sum of shipment imbalance of all the shipments that can be formed from the given sequence of parcels.

##### LEET CODE SIMILAR PROBLEM:

Explanation:

https://leetcode.com/problems/sum-of-subarray-ranges/discuss/1625501/JavaScript-All-Solutions-With-a-Step-by-Step-Tackling-of-the-Problem

You are given an integer array `nums`. The **range** of a subarray of `nums` is the difference between the largest and smallest element in the subarray.

Return *the **sum of all** subarray ranges of* `nums`*.*

A subarray is a contiguous **non-empty** sequence of elements within an array.

```js
// O(n) time | O(n) space
var subArrayRanges = function(nums) {
	/**
	 * The max range for each value in a negative copy of the array will be the min range...
	 * for the same value in the positive array.
	 */
	const N = nums.map(n => -n)
	return getMaxRange(nums) + getMaxRange(N)

	function getMaxRange(nums) {
		/**
		 * Monotonic stack initialized with a -1 for potential edge cases where we have...
		 * no values in the stack and we wanna calculate the left range of the poped number.
		 */
		const S = [-1]
		nums.push(Infinity)
		let res = 0
		for (let i = 0; i < nums.length; i++) {
			/**
			 * If we're poping values that're smaller than us that mean we gonna end up with a...
			 * boundary to our left that's greater than us, meaning we extended our range to include...
			 * all of the values that're smaller than us, meaning we got the full left range...
			 * in which we are the max.
			 */
			/**
			 * We will get the right range when a value from future position in the array pop us out...
			 * that's why we have an Infinity value at the end of the array that will pop the last...
		  	 * number out!
			 */
			while (nums[S[S.length - 1]] < nums[i]) {
				const MOST_MAX = S.pop(),
					LEFT_BOUNDARY = S[S.length - 1]
				const LEFT_RANGE = MOST_MAX - LEFT_BOUNDARY,
					RIGHT_RANGE = i - MOST_MAX
				/**
				 * By multiplying all these 3 values we get exactly how many times this number...
				 * was a max in its range!
				 */
				res += nums[MOST_MAX] * LEFT_RANGE * RIGHT_RANGE
			}
			S.push(i)
		}
		return res
	}
};
```

