# Problem Statement: [https://leetcode.com/problems/majority-element/description/](https://leetcode.com/problems/majority-element/description/)
# My Solution: 
```
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        map<int, int> m;
        int maximum = 0;
        for(auto i : nums)
        {
            m[i]++;
            if(m[i] > maximum)
                maximum = m[i];
        }
        for(auto i : nums)
            if(m[i] == maximum)
                return i;
        return 0;
    }
};
```
