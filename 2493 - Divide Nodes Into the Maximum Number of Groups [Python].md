# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/divide-nodes-into-the-maximum-number-of-groups/description/?envType=daily-question&envId=2025-01-30)
# My Solution: 
```python
class Solution:
    def magnificentSets(self, n: int, edges: List[List[int]]) -> int:
        
        graph = [[] for _ in range(n + 1)]

        for a, b in edges:
            graph[a].append(b)
            graph[b].append(a)

        def BFS(graph, x):

            q = deque()
            visited = [False] * (n + 1)
            levels = [0] * (n + 1)

            q.append(x)
            visited[x] = True
            levels[x] = 1

            max_level = 0

            while q:

                node = q.popleft()

                max_level = max(max_level, levels[node])

                for neighbor in graph[node]:
                    if levels[node] == levels[neighbor]:
                        return -1
                    if not visited[neighbor]:

                        q.append(neighbor)
                        visited[neighbor] = True
                        levels[neighbor] = levels[node] + 1

            return max_level

        result = 0

        def DFS(graph, visited, x):

            visited.append(x)
            seen[x] = True

            for y in graph[x]:
                if y not in visited:
                    DFS(graph, visited, y)

        seen = [False] * (n + 1)

        for i in range(1, n + 1):

            if seen[i]:
                continue

            visited = []

            DFS(graph, visited, i)

            maximum = -1

            for j in visited:

                v = BFS(graph, j)

                if v == -1:
                    return -1

                maximum = max(maximum, v)

            result += maximum

        return result
```
