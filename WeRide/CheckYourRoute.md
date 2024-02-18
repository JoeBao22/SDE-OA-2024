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