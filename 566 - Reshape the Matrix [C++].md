# Problem Statement: [https://leetcode.com/problems/reshape-the-matrix/description/](https://leetcode.com/problems/reshape-the-matrix/description/)
# My Solution: 
```c
class Solution {
public:
    vector<vector<int>> matrixReshape(vector<vector<int>>& mat, int r, int c) {
        int m = mat.size();
        int n = mat[0].size();
        if(m*n != r*c)
            return mat;
        else 
        {
            int a[r+1][c+1];
            int cont = 0;
            for(auto i : mat)
                for(auto j : i)
                {
                    a[cont/c][cont%c] = j;
                    cont++;
                }
            vector<vector<int>> newMat(r, std::vector<int>(c, 0));
            for(int i = 0;i < r;i++)
                for(int j = 0;j < c;j++)
                    newMat[i][j] = a[i][j];
            return newMat;
        }
    }
};
```
