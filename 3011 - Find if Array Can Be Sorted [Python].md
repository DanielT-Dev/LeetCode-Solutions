# Problem Statement: [https://leetcode.com/problems/find-if-array-can-be-sorted/description/](https://leetcode.com/problems/find-if-array-can-be-sorted/description/) 
# My Solution: 
```py
class Solution:
    def canSortArray(self, nums: List[int]) -> bool:
        
        # We can consider all continuous sequences with the specified property as a group
        # We know that any such group can be sorted
        # Proof: by picking the maximum element and moving it to the rightmost place in the group and then repeating this algorithm for the rest of the elements
        # All we have to check is that the groups form a sorted array
        # i.e. the maximum of the previous group is less than the minimum of the current group

        groups = []

        previous = None
        previous_bits = 0
        current_bits = 0
        current_min = float("inf")
        current_max = 0

        for n in nums:
            current_bits = n.bit_count()

            if previous != None:
                if previous_bits == current_bits:
                    pass
                else:
                    groups.append((current_min, current_max))
                    current_min = n
                    current_max = n

            current_min = min(current_min, n)
            current_max = max(current_max, n)

            previous = n

            previous_bits = current_bits

        # Consider last group too
        groups.append((current_min, current_max))

        # (Debugging)
        # print(groups)

        previous = None
        
        for group in groups:
            if previous != None:
                if previous[1] > group[0]:
                    return False
            
            previous = group

        return True

        # Time Complexity O(n)
```
