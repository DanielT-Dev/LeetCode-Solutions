# Problem statement: [link to the problem](https://leetcode.com/problems/adjacent-increasing-subarrays-detection-i/?envType=daily-question&envId=2025-10-14)
# My Solution:
```js
/**
 * @param {number[]} nums
 * @param {number} k
 * @return {boolean}
 */
var hasIncreasingSubarrays = function(nums, k) {
    const n = nums.length;
    let c1 = 0, c2 = 0;

    // Edge case
    if(k === 1)
        return true;

    // Form window 1
    for(let i = 1; i < k; i++)
        if(nums[i - 1] < nums[i])
            c1++;
    // Form window 2
    for(let i = k + 1; i < 2 * k; i++)
        if(nums[i - 1] < nums[i])
            c2++;

    // Initial check
    if(c1 === k - 1 && c2 === k - 1)
        return true;

    // Sliding window(s)
    for(let i = 2 * k; i < n; i++){

        // Window 2 recieves a an element on the right
        if(nums[i - 1] < nums[i]) c2 ++;
        // Window 1 recieves a an element on the right
        if(nums[i - k - 1] < nums[i - k]) c1 ++;
        // Window 2 loses an element on the left
        if(nums[i - k] < nums[i - k + 1]) c2 --;
        // Window 1 loses an element on the left
        if(nums[i - 2 * k] < nums[i - 2 * k + 1]) c1 --;

        // For debugging
        // console.log(c1, c2);

        // Check
        if(c1 === k - 1 && c2 === k - 1)
            return true;
    }

    // No 2 adjacent increasing sub-arrays of legnth k have been found
    return false;
};
```
