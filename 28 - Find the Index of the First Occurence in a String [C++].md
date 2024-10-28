# Problem Statement: [https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/description/](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/description/)
# My Solution:
```
class Solution {
public:
    int strStr(string haystack, string needle) {
        int haystackLength = haystack.length();
        int needleLength = needle.length();

        for(int i = 0;i < haystackLength;i++)
        {
            if(haystack[i] == needle[0])
            {
                int t = i;
                
                while(haystack[i] == needle[i-t] && i-t+1 <= needleLength)
                    i++;
                i--;
                if(i-t+1 == needleLength)
                    return t;
                i = t;
            }
        }

        return -1;
    }
};
```
