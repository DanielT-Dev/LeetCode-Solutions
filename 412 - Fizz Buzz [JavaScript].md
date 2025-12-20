# Problem Statement: [https://leetcode.com/problems/fizz-buzz/](https://leetcode.com/problems/fizz-buzz/)
# My Solution: 
```js /**
 * @param {number} n
 * @return {string[]}
 */
var fizzBuzz = function(n) {
    let answer = new Array(n);

    for (let i = 0; i < n; i ++) {
        if((i + 1) % 5 === 0 && (i + 1) % 3 === 0)
            answer[i] = "FizzBuzz";
        else if((i + 1) % 5 === 0)
            answer[i] = "Buzz";
        else if((i + 1) % 3 === 0)
            answer[i] = "Fizz";
        else
            answer[i] = String(i + 1);
    }

    return answer;
};
```
