# Problem Statement: [https://leetcode.com/problems/maximize-happiness-of-selected-children/description/?envType=daily-question&envId=2025-12-25](https://leetcode.com/problems/maximize-happiness-of-selected-children/description/?envType=daily-question&envId=2025-12-25)
# My Solution: 
```js
/**
 * @param {number[]} happiness
 * @param {number} k
 * @return {number}
 */
var maximumHappinessSum = function(happiness, k) {
    const n = happiness.length;
    let d = 0, result = 0;
    happiness.sort((a, b) => b - a);

    for (let i = 0; i < k; i ++) {
        if (happiness[i] - d > 0)
            result += happiness[i] - d;
        else
            return result;
        d += 1;
    };

    return result;
};
```
