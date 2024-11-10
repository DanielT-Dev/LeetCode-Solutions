# Problem Statement: [https://leetcode.com/problems/intersection-of-two-arrays-ii/description/](https://leetcode.com/problems/intersection-of-two-arrays-ii/description/)
# My Solution: 
```c
class Solution {
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
        vector<int> ans;
        map<int, int> m1, m2;

        for(auto i : nums1)
            m1[i] = 0;
        for(auto i : nums2)
            m2[i] = 0;

        for(auto i : nums1)
            m1[i]++;
        for(auto i : nums2)
            m2[i]++;

        int n = nums1.size();
        sort(nums1.begin(), nums1.end());

        for(int i = 0;i < n;i++)
        {
            if((i == 0 || nums1[i] != nums1[i-1]) && m1[nums1[i]] > 0 && m2[nums1[i]] > 0)
            {
                int minFreq = min(m1[nums1[i]], m2[nums1[i]]);

                for(int j = 1;j <= minFreq;j++)
                    ans.push_back(nums1[i]);
            }
        }
        
        return ans;
    }
};
```
