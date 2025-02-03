# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/apply-transform-over-each-element-in-array/description/)
# My Solution: 
```js
/**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var map = function(arr, fn) {

    for(i = 0 ; i < arr.length ; i ++)
    {
        arr[i] = fn(arr[i], i)
    }

    return arr
    
};
```
