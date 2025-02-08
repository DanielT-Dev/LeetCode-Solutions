# Statement: [Link to Leetcode](https://leetcode.com/problems/design-a-number-container-system/description/)
# Solution:
```python
from sortedcontainers import SortedList

class NumberContainers:
    def __init__(self):
        self.dict1 = {}
        self.dict2 = defaultdict(SortedList)

    def change(self, index, number):
        if index in self.dict1:
            num = self.dict1[index]
            self.dict2[num].remove(index)

        self.dict1[index] = number 
        self.dict2[number].add(index)

    def find(self, number):
        if not self.dict2[number]:
            return - 1 

        return self.dict2[number][0]
```
