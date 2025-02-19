# Statement: [Link to Leetcode](https://leetcode.com/problems/additive-number/)
# Solution:
```python
class Solution:
    def isAdditiveNumber(self, num: str) -> bool:
        n = len(num)
        
        def backtrack(index, sequence):
            if index == n and len(sequence) >= 3:
                return True
            
            for i in range(index, n):
                current_num = num[index:i+1]
                
                # Skip numbers with leading zeros unless it's "0"
                if len(current_num) > 1 and current_num[0] == '0':
                    continue
                
                current_num = int(current_num)
                
                if len(sequence) < 2 or current_num == sequence[-1] + sequence[-2]:
                    if backtrack(i+1, sequence + [current_num]):
                        return True
            
            return False
        
        return backtrack(0, [])
```
