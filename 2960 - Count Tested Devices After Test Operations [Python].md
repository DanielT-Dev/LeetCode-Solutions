# Statement: [Link to Leetcode](https://leetcode.com/problems/count-tested-devices-after-test-operations/description/)
# Solution:
```python
class Solution:
    def countTestedDevices(self, batteryPercentages: List[int]) -> int:
        
        n = len(batteryPercentages)

        counter = 0

        for i in range(n):
            if batteryPercentages[i] - counter > 0:
                counter += 1

        return counter
```
