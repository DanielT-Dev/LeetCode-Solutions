# Problem Statement: [https://leetcode.com/problems/set-mismatch/?envType=problem-list-v2&envId=dsa-linear-shoal-array-ii](https://leetcode.com/problems/set-mismatch/?envType=problem-list-v2&envId=dsa-linear-shoal-array-ii)
# My Solution: 
```js
/**
 * @param {number[]} nums
 * @return {number[]}
 */
var findErrorNums = function(nums) {
    const n = nums.length, target = n * (n + 1) / 2, s = nums.reduce((a, b) => a + b, 0);
    let f = new Map();

    for(let i = 0;i < n;i++) {
        if (!f.has(nums[i]))
            f.set(nums[i], 0);
        f.set(nums[i], f.get(nums[i]) + 1);

        if(f.get(nums[i]) === 2)
            return [nums[i], target - s + nums[i]];
    }
};
```
