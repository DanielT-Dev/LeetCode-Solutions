# Problem Statement: 
# My Solution: 
```
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        vector<int> t;
        int i = 0, j = 0;
        while(i < m && j < n)
            if(nums1[i] < nums2[j])
                t.push_back(nums1[i++]);
            else 
                t.push_back(nums2[j++]);
        while(i < m)
            t.push_back(nums1[i++]);
        while(j < n)
            t.push_back(nums2[j++]);
        for(int i = 0;i < m+n;i++)
            nums1[i] = t[i];
    }
};
```
