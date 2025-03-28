# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/kth-largest-element-in-a-stream/?envType=problem-list-v2&envId=design)
# My Solution: 
```python
class KthLargest:

    def __init__(self, k: int, nums: List[int]):
        
        n = len(nums)

        self.queue = []
        self.k = k

        heapq.heapify(self.queue)

        nums.sort()
        
        i = 0
        while i < k and i < n:
            heapq.heappush(self.queue, nums[i + n - k])
            i += 1


    def add(self, val: int) -> int:

        if len(self.queue) == 0:
            heapq.heappush(self.queue,val)
            return val

        heapq.heappush(self.queue, val)      

        if len(self.queue) > self.k:  
            heapq.heappop(self.queue)
        
        return self.queue[0]


# Your KthLargest object will be instantiated and called as such:
# obj = KthLargest(k, nums)
# param_1 = obj.add(val)
```
