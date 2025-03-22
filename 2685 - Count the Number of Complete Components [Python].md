# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/count-the-number-of-complete-components/description/?envType=daily-question&envId=2025-03-22)
# My Solution: 
```python
class Solution:
    def countCompleteComponents(self, n: int, edges: List[List[int]]) -> int:
        
        graph = [[] for _ in range(n)]
        edge_counter = 0
        node_counter = 0
        result = 0

        for a, b in edges:
            graph[a].append(b)
            graph[b].append(a)
        
        def dfs(node, adj, visited):

            nonlocal edge_counter, node_counter

            visited[node] = True
            node_counter += 1
            edge_counter += len(adj[node])

            for nei in adj[node]:
                if not visited[nei]:
                    dfs(nei, adj, visited)
        
        visited = [False] * n
        
        for i in range(n):

            if not visited[i]:
                dfs(i, graph, visited)

                if edge_counter == (node_counter * (node_counter - 1)):
                    result += 1

                edge_counter = node_counter = 0

        return result
```
