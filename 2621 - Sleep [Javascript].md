# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/sleep/description/)
# My Solution: 
```js
/**
 * @param {number} millis
 * @return {Promise}
 */
async function sleep(millis) {
    return new Promise(resolve => setTimeout(resolve, millis));
}

/** 
 * let t = Date.now()
 * sleep(100).then(() => console.log(Date.now() - t)) // 100
 */
```
