# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/remove-nth-node-from-end-of-list/description/)
# My Solution: 
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        
        arr = []

        while head:

            arr.append(head.val)
            head = head.next
        
        sz = len(arr)

        dummy = current = ListNode(0)

        i = 0

        while i < sz:

            if i == sz - n:
                i += 1
                continue
            else:
                current.next = ListNode(arr[i])
                current = current.next
            
            i += 1
        
        return dummy.next
```
