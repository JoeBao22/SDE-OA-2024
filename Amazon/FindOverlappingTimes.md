# FindOverlappingTime

A Supply Chain Manager at an Amazon warehouse is reviewing the logs of when trucks arrived at and departed from their warehouse. Please help them with their review by completing the following challenge: Given a collection of time intervals, [start, end], merge and return the
overlapping intervals sorted in ascending order of their start times.
### Example
intervals = [[7, 7], [2, 3], [6, 11], [1, 2]]
The interval [1, 2] merges with [2, 3] while [7, 7] merges with [6, 11]. There are no more overlapping intervals. The answer is [[1, 3], [6, 11]].
### Function Description
Complete the function findOverlapping Times in the editor below.
findOverlapping Times has the following parameter(s):
- int intervals[[n][2]]: the time intervals

### Returns
int[][2]: the merged intervals in sorted order
Constraints
- $1 \le n \le 10^5$
- $1 \le intervals[i][2] \le 10^9$
- $ intervals[i][0] \le intervals[i][1]$ for all i.

### Solution

```Python
def findOverlappingIntervals(intervals):
    intervals.sort()
    if not intervals:
        return []
    result = [intervals[0]]
    for i in range(1, len(intervals)):
        start, end = intervals[i]
        if start <= result[-1][1]:
            result[-1] = (result[-1][0], max(end, result[-1][1]))
        else:
            result.append(intervals[i])
    return result 
```