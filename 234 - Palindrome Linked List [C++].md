# Problem Statement: [https://leetcode.com/problems/palindrome-linked-list/description/](https://leetcode.com/problems/palindrome-linked-list/description/)
# My Solution: 
```c
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
    bool isPalindrome(ListNode* head) {
        string a = "";
        while(head)
        {
            a += head->val + '0';
            head = head->next;
        }
        int n = a.length();
        for(int i = 0;i < n / 2;i++)
            if(a[i] != a[n - i - 1])
                return false;
        return true;
    }
};
```
