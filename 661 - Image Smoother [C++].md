# Problem Statement: [https://leetcode.com/problems/image-smoother/description/](https://leetcode.com/problems/image-smoother/description/)
# My Solution: 
```cpp
class Solution {
public:
    vector<vector<int>> imageSmoother(vector<vector<int>>& img) {
        int m = img.size();
        int n = img[0].size();
        vector<vector<int>> newMatrix(m, vector<int>(n, 0));
        const int di[9] = {-1, -1, -1, 0, 0, 0, 1, 1, 1},
        dj[9] = {-1, 0, 1, -1, 0, 1, -1, 0, 1};
        for(int i = 0;i < m;i++)
            for(int j = 0;j < n;j++)
            {
                int sum = 0;
                int counter = 0;
                for(int d = 0;d < 9;d++)
                {
                    int newI = i+di[d];
                    int newJ = j+dj[d];
                    if(newI >= 0 && newI <m && newJ >= 0 && newJ < n)
                    {
                        sum += img[newI][newJ];
                        counter++;
                    }
                }
                newMatrix[i][j] = sum/counter;
            }
        return newMatrix;
    }
};
```
