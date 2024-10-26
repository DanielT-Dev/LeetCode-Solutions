# Problem Statement: [https://leetcode.com/problems/longest-common-prefix/description/](https://leetcode.com/problems/longest-common-prefix/description/)
# My Solution: 
```
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        int depth = 0;
        string answer = "";
        int lengthOfArray = strs.size();
        int maximumLength = 0;

        for(int i = 0;i < lengthOfArray;i++)
            if(strs[i].length() > maximumLength)
                maximumLength = strs[i].length();

        while(depth < maximumLength)
        {
            bool willWorkForAll = true;

            char currentIdenticalCharacter = strs[0][depth];

            for(int i = 0;i < lengthOfArray;i++)
                if(strs[i][depth] != currentIdenticalCharacter)
                {
                    willWorkForAll = false;
                    break;
                }

            if(willWorkForAll)
            {
                answer += currentIdenticalCharacter;
                depth++;
            }
            else
                return answer;
        }

        return answer;
    }
};
```
