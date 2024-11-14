# Problem Statement: [https://leetcode.com/problems/next-greater-element-i/description/](https://leetcode.com/problems/next-greater-element-i/description/)
# My Solution: 
```c
class Solution {
public:
    vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
        vector<int> ans;
        int n1 = nums1.size();
        int n2 = nums2.size();

        stack<int> s;
        vector<int> v(n2);

        for(int i = n2-1;i>= 0;i--)
        {
            while(!s.empty() && s.top() < nums2[i])
                s.pop();
            if(s.empty())
                v[i] = -1;
            else 
                v[i] = s.top();
            s.push(nums2[i]);
        }

        for(int i = 0;i < n1;i++)
            for(int j = 0;j < n2;j++)
                if(nums1[i] == nums2[j])
                    ans.push_back(v[j]);

        return ans;
    }
};
```
