# Problem Statement: [https://leetcode.com/problems/degree-of-an-array/description/](https://leetcode.com/problems/degree-of-an-array/description/)
# My Solution: 
```cpp
class Solution {
public:
    int findShortestSubArray(vector<int>& nums) {
        unordered_map<int, int> m;
        int degree = 0, ans = INT_MAX;
        for(auto i : nums)
        {
            m[i]++;
            if(m[i] > degree)
                degree = m[i];
        }
        if(degree == 1)
            return 1;
        for(auto e : m)
        {
            if(e.second == degree)
            {
                int n = nums.size(), start = -1, end = n;
                for(int i = 0;i < n && nums[i] != e.first;i++)
                    start = i;
                for(int i = n-1;i >= 0 && nums[i] != e.first;i--)
                    end = i;
                start++;
                end--;
                cout<<e.first<<':'<<start<<' '<<end<<'\n';
                if(end-start+1 < ans)
                    ans = end-start+1;
            }
        }
        return ans;
    }
};
```
