# Statement: [Link to Leetcode](https://leetcode.com/problems/the-k-th-lexicographical-string-of-all-happy-strings-of-length-n/description/?envType=daily-question&envId=2025-02-19)
# Solution:
```python
class Solution:
    def getHappyString(self, n: int, k: int) -> str:
        
        '''
        Divide And Conquer - Binary Search Method

        Intuition: 

        Starting with an empty string we can append a new letter
        from the set in 3 possible ways ('a', 'b', 'c').

        All strings obtained by starting with 'a' will be
        lexicographycally lower than the ones starting with
        'b' and 'c'.

        In the same way, all strings starting with 'b' will be 
        lexicographically lower than the ones starting with 'c'.

        -------------------------
        Time Complexity: O(log n)
        Space Complexity: O(1)
        -------------------------
        '''

        # Store result
        result = []

        def binary_search(left, right, avaiable):
            nonlocal result

            # Exit condition
            if not left < right:
                return

            previous = result[-1]

            low_choice = avaiable[0]
            high_choice = avaiable[1]

            middle = (left + right) // 2

            if k <= middle:
                result.append(low_choice)
                binary_search(left, middle, tuple(sorted([previous, high_choice])))

            else:
                result.append(high_choice)
                binary_search(middle + 1, right, tuple(sorted([previous, low_choice])))

        # t = 2 ^ (n - 1)
        t = 1 << (n - 1)

        if k >= 1 and k <= t:
            result.append('a')
            binary_search(1, t, ('b', 'c'))

        elif k >= t + 1 and k <= 2 * t:
            result.append('b')
            binary_search(t + 1, 2 * t, ('a', 'c'))

        elif k >= 2 * t + 1 and k <= 3 * t:
            result.append('c')
            binary_search(2 * t + 1, 3 * t, ('a', 'b'))

        # Edge case
        if len(result) == 0:
            return ""

        return "".join(result)
```
