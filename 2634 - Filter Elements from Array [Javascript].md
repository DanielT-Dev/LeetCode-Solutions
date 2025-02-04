# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/filter-elements-from-array/)
# My Solution: 
```js
/**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var filter = function(arr, fn) {

    let new_arr = []
    let n = arr.length

    for(let i = 0; i < n; i ++)
    {
        if(fn(arr[i], i))
            new_arr.push(arr[i])
    }

    return new_arr
    
};
```
