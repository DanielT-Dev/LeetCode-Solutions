# Problem Statement: [https://leetcode.com/problems/intersection-of-two-linked-lists/description/](https://leetcode.com/problems/intersection-of-two-linked-lists/description/)
# My Solution: 
```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode* copyA = headA;
        ListNode* copyB = headB;
        vector<ListNode*> vA;
        vector<ListNode*> vB;

        while(copyA)
        {
            vA.push_back(copyA);
            copyA = copyA->next;
        }
        while(copyB)
        {
            vB.push_back(copyB);
            copyB = copyB->next;
        }

        int iA = vA.size()-1;
        int iB = vB.size()-1;

        while(iA >= 0 && iB >= 0 && vA[iA] == vB[iB])
        {
            iA--;
            iB--;
        }
        iA++;
        iB++;

        int steps = iA;

        copyA = headA;
        for(int i = 1;i <= steps;i++)
            copyA = copyA->next;

        return copyA;
    }
};
```
