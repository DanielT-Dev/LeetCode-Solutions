# Problem Statement: [https://leetcode.com/problems/1-bit-and-2-bit-characters/description/](https://leetcode.com/problems/1-bit-and-2-bit-characters/description/)
# My Solution: 
```cpp
class Solution {
public:
    bool isOneBitCharacter(vector<int>& bits) {
        int i = 0, n = bits.size();
        while(i < n)
        {
            if(bits[i] == 1)
                i++;
            else if(bits[i] == 0)
            {
                if(i == n-1)
                    return true;
            }
            i++;
        }
        return false;
    }
};
```
