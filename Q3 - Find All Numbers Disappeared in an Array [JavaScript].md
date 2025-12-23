# Problem Statement: [https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/?envType=problem-list-v2&envId=dsa-linear-shoal-array-ii](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/?envType=problem-list-v2&envId=dsa-linear-shoal-array-ii)
# My Solution: 
```js
/**
 * @param {number[]} nums
 * @return {number[]}
 */
var findDisappearedNumbers = function(nums) {
    const n = nums.length;
    let seen = new Array(n + 1).fill(false);

    for(let i = 0;i < n;i++)
        seen[nums[i]] = true;

    let result = [];
    for(let i = 1;i <= n;i++)
        if(seen[i] === false)
            result.push(i);

    return result;
};
```
