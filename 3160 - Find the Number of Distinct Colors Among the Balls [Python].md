# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/find-the-number-of-distinct-colors-among-the-balls/description/?envType=daily-question&envId=2025-02-07)
# My Solution: 
```python
class Solution:
    def queryResults(self, limit: int, queries: List[List[int]]) -> List[int]:
        
        distinct_colors = 0

        color_of_ball = {}
        colors_frequency = {}

        result = []

        for ball, color in queries:

            previous_color = "none"

            if ball in color_of_ball:
                previous_color = color_of_ball[ball]

            if previous_color is not "none":
                colors_frequency[previous_color] -= 1

                # A new color has just been deleted, update total
                if colors_frequency[previous_color] == 0:
                    distinct_colors -= 1

            # Set new ball color
            color_of_ball[ball] = color

            if color not in colors_frequency:
                colors_frequency[color] = 0

            colors_frequency[color] += 1

            # A new color has just been added, update total
            if colors_frequency[color] == 1:
                distinct_colors += 1

            result.append(distinct_colors)

        return result

```
