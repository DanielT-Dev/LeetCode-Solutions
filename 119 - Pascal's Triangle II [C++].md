# Problem Statement: [https://leetcode.com/problems/pascals-triangle-ii/description/](https://leetcode.com/problems/pascals-triangle-ii/description/)
# My Solution: 
```
class Solution {
public:
    vector<int> getRow(int rowIndex) {
        vector<int> v;
        v.push_back(1);
        if(rowIndex == 0)
            return v;
        v.push_back(1);
        if(rowIndex == 1)
            return v;
        for(int i = 2;i <= rowIndex;i++)
        {
            vector<int> newV;

            newV.push_back(1);
            for(int j = 1;j < i;j++)
                newV.push_back(v[j-1]+v[j]);
            newV.push_back(1);

            v.clear();

            for(auto j : newV)
                v.push_back(j);
        }

        return v;
    }
};
```
