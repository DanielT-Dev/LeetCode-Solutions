# Problem Statement: [https://leetcode.com/problems/remove-duplicates-from-sorted-list/description/](https://leetcode.com/problems/remove-duplicates-from-sorted-list/description/) 
# My Solution: 
```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) 
    {
        ListNode* current = head;

        while(current)
        {
            while(current->next && current->val == current->next->val)
                current->next = current->next->next;
            current = current->next;
        }

        return head;
    }
};
```
