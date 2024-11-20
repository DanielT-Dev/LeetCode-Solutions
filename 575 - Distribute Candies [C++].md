# Problem Statement: [https://leetcode.com/problems/distribute-candies/submissions/1136768496/](https://leetcode.com/problems/distribute-candies/submissions/1136768496/)
# My Solution: 
```c
class Solution {
public:
    int distributeCandies(vector<int>& candyType) {
        map<int, int> m;
        for(auto i : candyType)
            m[i] = 0;
        for(auto i : candyType)
            m[i]++;
        return min(m.size(), candyType.size()/2);
    }
};
```
