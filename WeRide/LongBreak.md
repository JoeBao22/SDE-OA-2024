# Long Break

You are organizing an event where there will be a number of presenters. The event starts at time 0 and time be allocated for networking at any time during the event when there is not a presentation being made. The presentations may not overlap as they are in the same room, but this allows them to run consecutively, without breaks. While the order of speeches cannot be changed, there is a maximum number given that indicates how many speeches may be rescheduled. 

Your goal is to maximize the length of the longest networking period you can arrange.
For example, there are n = 4 presenters scheduled for the course of the event which begins at time 0 and ends at time t = 15. The meetings start at times start = [4, 6, 7, 10] and end at times finish = [5, 7, 8, 11]. You can rearrange up to k = 2 meetings. 

In this case, we have 4 periods without speakers scheduled: [(0-3), (5), (8-9), (11-14)]. The meeting ends after hour 14. If the first meeting is shifted to an hour later, a break is created from 0 to 5, 5 hours. If the last speech is moved up to 8, it will create a break from 9 to 15. The longest break will be 7

### Solution
```python
def maxBreak(start, end,t, k):
    zipped = list(zip(start, end))
    zipped.sort()
    start = [item[0] for item in zipped]
    end = [item[1] for item in zipped]
    k += 1
    intervals = []
    intervals.append(start[0])
    for i in range(1, len(start)):
        intervals.append(start[i] - end[i-1])
    intervals.append(t - end[-1])
    current_sum = 0
    for i in range(k):
        current_sum += intervals[i]
    max_subarray_sum = current_sum
    for i in range(k, len(intervals)):
        current_sum += intervals[i] - intervals[i-k]
        max_subarray_sum = max(max_subarray_sum, current_sum)
    return max_subarray_sum
```