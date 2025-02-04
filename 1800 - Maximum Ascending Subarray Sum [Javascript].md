# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-ascending-subarray-sum/description/)
# My Solution: 
```js
/**
 * @param {number[]} nums
 * @return {number}
 */
var maxAscendingSum = function(nums) {
    
    let result = -Infinity
    let elo_taxi = nums[0]
    let n = nums.length

    for(let i = 1; i < n; i++)
    {
        if(nums[i - 1] < nums[i])
            elo_taxi += nums[i]
        else
        {
            result = Math.max(result, elo_taxi)

            elo_taxi = nums[i]
        }
    }

    result = Math.max(result, elo_taxi)

    return result
};
```
