# Check Your Route

A ride hailing company sometimes travels between cities. To avoid delays, a driver first checks for the shortest routes. There is a map of the cities and their bidirectional roads represented by a graph of nodes and edges. 

Determine the paths from the first node to the last node and choose the shortest length. Now select all paths that are that length. These are the shortest paths. Return an array of strings, one for each road in order, where the value is yes if the road is along any shortest path or no if it is not. The roads or edges are named using their 1-based index within the input arrays.

### Example
given a map of g nodes = 5 nodes, the starting nodes, ending nodes and road lengths are:
| Road |  from/to/weight|
| -- | ---|
| 1 | (1,2,1)|
| 2 | (2,3,1)|
| 3 | (3,4,1)|
| 4 |(4,5,1)|
| 5 | (5,1,3)|
| 6 | (1,3,2)|
| 7 | (5,3,1) |

The shortest path from 1 to 5 is 3. The final result is [YES, YES, No, No, Yes, Yes, Yes].

### Solution

```python
import defaultdict
import heapq


def find_shortest_paths(g_nodes, g_from, g_to, g_weight):
    for i in range(len(g_from)):
        s, t, w = g_from[i], g_to[i], g_weight[i]
        graph[s].append((t, w))
        graph[t].append((s, w))

    distance = {i : float("inf") for i in range(n+1)}
    distance[1] = 0
    h = [(0, 1)]
    while h:
        dist, current_node = heapq.heappop(h)
        if dist > distance[current_node]:
            continnue
        else:
            for nxt, w in graph[current_node]:
                new_distance = distance[current_node] + w
                if new_distance < distance[nxt]:
                    distance[nxt] = new_distance
                    heapq.heappush(h, (new_distance, nxt))
         
    shortest = []
    def dfs(path, node):
        if node == 1:
            shortest.append(list(path))
            return
        for nxt, w in graph[node]:
            if distance[nxt] == distance[node] - weight:
                path.append((node, nxt))
                dfs(path, nxt)
                path.pop()
    dfs([], n)

    marked = set()
    for path in shortest_paths:
        for edge in path:
            marked.add(edge)
    result = []
    for i in range(len(g_from)):
        s, t = g_from[i], g_to[i]
        if (s, t) in marked or (t, s) in marked:
            result.append("YES")
        else:
            result.append("NO")
    return result




```