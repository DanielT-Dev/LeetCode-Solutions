# Problem Statement: [https://leetcode.com/problems/island-perimeter/description/](https://leetcode.com/problems/island-perimeter/description/)
# My Solution: 
```c
class Solution {
public:

    bool isInMatrix(int x, int y, int m, int n)
    {
        return x >= 0 && x < m && y >= 0 && y < n;
    }

    const int di[4] = {-1, 0, 1, 0}, dj[4] = {0, 1, 0, -1};

    int islandPerimeter(vector<vector<int>>& grid) {
        int ans = 0;
        int m = grid.size();
        int n = grid[0].size();
        for(int i = 0;i < m;i++)
            for(int j = 0;j < n;j++)
                if(grid[i][j] == 1)
                {
                    int c = 0;
                    for(int d = 0;d < 4;d++)
                    {
                        int ni = i+di[d];
                        int nj = j+dj[d];
                        
                        if(!isInMatrix(ni, nj, m, n) || grid[ni][nj] == 0)
                            c++;
                    }
                    ans += c;
                }

        return ans;
    }
};
```
