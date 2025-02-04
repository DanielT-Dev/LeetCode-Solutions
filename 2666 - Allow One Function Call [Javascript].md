# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/allow-one-function-call/description/)
# My Solution: 
```js
/**
 * @param {Function} fn
 * @return {Function}
 */
var once = function(fn) {
    
    let has_been_called = false

    return function(...args){

        if (!has_been_called){

            has_been_called = true

            return fn(...args)
            
        }
    }
};

/**
 * let fn = (a,b,c) => (a + b + c)
 * let onceFn = once(fn)
 *
 * onceFn(1,2,3); // 6
 * onceFn(2,3,6); // returns undefined without calling fn
 */
```
