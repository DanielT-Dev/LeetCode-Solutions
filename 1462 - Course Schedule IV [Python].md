# Problem Statement: [Link to LeetCode](https://leetcode.com/problems/course-schedule-iv/description/?envType=daily-question&envId=2025-01-27)
# My Solution: 
```python
class Solution:
    def checkIfPrerequisite(self, numCourses: int, prerequisites: List[List[int]], queries: List[List[int]]) -> List[bool]:

        n = numCourses

        # Build directed garph (adjacency list)
        graph = [[] for _ in range(n)]

        for a, b in prerequisites:
            # Directed edge from node 'a' to node 'b'
            graph[a].append(b)

        # Depth-First Search (DFS)
        def DFS(graph, visited, x, root):
            visited[x] = True

            # Node 'x' is reachable from node 'root'
            reachable[root][x] = True

            for y in graph[x]:
                if not visited[y]:
                    DFS(graph, visited, y, root)

        # Store reachability of all pairs of nodes in an n * n matrix
        # All elements are initialized with the value 'False'
        reachable = [[False] * n for _ in range(n)]

        for i in range(n):
            visited = [False] * n
            DFS(graph, visited, i, i)

        result = []

        # Answer queries in O(1) (constant) time complexity
        for a, b in queries:
            if reachable[a][b]:
                result.append(True)
            else:
                result.append(False)

        return result
```
