# Problem Statement: [https://leetcode.com/problems/flood-fill/description/](https://leetcode.com/problems/flood-fill/description/)
# My Solution: 
```cpp
class Solution {
public:
    vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int color) {
        int source_color = image[sr][sc];
        int m = image.size();
        int n = image[0].size();
        queue<pair<int, int>> q;
        q.push({sr, sc});
        const int di[4] = {0, -1, 0, 1}, dj[4] = {1, 0, -1, 0};
        while(!q.empty())
        {
            int i = q.front().first;
            int j = q.front().second;
            q.pop();
            image[i][j] = -1;
            for(int d = 0;d < 4;d++)
            {
                int new_i = i+di[d];
                int new_j = j+dj[d];
                if(is_in_matrix(new_i, new_j, m, n) && image[new_i][new_j] == source_color)
                    q.push({new_i, new_j});
            }
        }
        vector<vector<int>> ans(m, vector<int>(n, 0));
        for(int i = 0;i < m;i++)
            for(int j = 0;j < n;j++)
                if(image[i][j] == -1)
                    ans[i][j] = color;
                else 
                    ans[i][j] = image[i][j];
        return ans;
    }

    bool is_in_matrix(int i, int j, int m, int n)
    {
        return i >= 0 && i < m && j >= 0 && j < n;
    }
};
```
