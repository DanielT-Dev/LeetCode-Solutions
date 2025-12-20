# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/is-subsequence/description/)
# My Solution: 
```js
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isSubsequence = function(s, t) {
    
    let m = s.length, n = t.length, previous = -1;

    // Check if each character from string s appears in string t in order
    // Time Complexity: O(n^2)
    for (let i = 0;i < m;i++) {
        let found = false;
        for (let j = previous + 1;j < n;j++)
            if(s[i] === t[j]){
                previous = j;
                found = true;
                break;
            }
        if(found === false)
            return false;
    }
    return true;
};
```
