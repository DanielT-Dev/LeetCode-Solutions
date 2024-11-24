# Problem Statement: [https://leetcode.com/problems/can-place-flowers/description/](https://leetcode.com/problems/can-place-flowers/description/)
# My Solution: 
```cpp
class Solution {
public:
    bool canPlaceFlowers(vector<int>& flowerbed, int n) {
        for(int i = 0;i < flowerbed.size();i++)
            if(flowerbed[i] == 1)
                i++;
            else if(flowerbed[i] == 0 && (i+1 == flowerbed.size() ||flowerbed[i+1] == 0))
            {
                i++;
                n--;
            }
        return n <= 0;
    }
};
```
