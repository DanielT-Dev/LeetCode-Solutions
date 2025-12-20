# Problem Statement: [https://leetcode.com/problems/perfect-number/description/](https://leetcode.com/problems/perfect-number/description/)
# My Solution: 
```js
/**
 * @param {number} num
 * @return {boolean}
 */
var checkPerfectNumber = function(num) {
    let n = 0;

    for (let i = 1; i <= Math.floor(num / 2); i ++) {
        if(num % i === 0)
            n += i;
    }

    return n === num;
};
```
