# Problem Statement: [https://leetcode.com/problems/intersection-of-two-arrays/description/](https://leetcode.com/problems/intersection-of-two-arrays/description/) 
# My Solution: 
```c
class Solution {
public:
    vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
        vector<int> ans;
        map<int, int> m;
        
        for(auto i : nums1)
            m[i] = 1;
        for(auto i : nums2)
            if(m[i] == 1)
                m[i] = 2;
        
        for(auto i : m)
            if(i.second == 2)
                ans.push_back(i.first);
        
        return ans;
    }
};
```
