# Find Min Trips
There were a large number of orders placed on Amazon Prime Day. The orders are packed and are at the warehouse ready to be delivered. The delivery agent needs to deliver them in as few trips as possible.
In a single trip, the delivery agent can choose packages following either of two rules:
- Choose two packages with the same weight
- Choose three packages with the same weight
Determine the minimum number of trips required to deliver the packages. If it is not possible to deliver all of them, return -1.
### Example
packageweight = [2, 4, 6, 6, 4, 2, 4]

The agent needs a minimum of 3 trips as shown below. Return 3 as the answer.

n=7, [2, 4, 6, 6, 4, 2, 4]
- First Trip: [2, 4, 6, 6, 4, 2, 4]. 2, 2 are chosen
- Second Trip： [4, 6, 6, 4, 4]. 4, 4, 4 are chosen.
- Third Trip [6, 6]. 6, 6 are chosen

### Function Description
Complete the function *findMinTrips* in the editor.
*findMinTrips* has the following parameter:
- int packageweight [n]: the weights of each package

### Returns:
- int: the minimum number of trips required or -1 if it is not possible to deliver them all

### Constraints:
- $1 \leq n \leq 10^5$
- $1 \leq packageweights[i] \leq 10^9$.


### Solution

```python
import math
def findMinTrips(packageweight):
    weight2counter = {}
    for weight in packageweight:
        if weight not in weight2counter:
            weight2counter[weight] = 1
        else:
            weight2counter[weight] += 1
    num_of_trips = 0
    for weight, count in weight2counter.items():
        if count == 1:
            return -1
        else:
            # 2->1; 3->1
            # 4->2; 5->2; 6->2
            # 7->3; 8->3; 9->3
            num_of_trips += math.ceil(count / 3)
    return num_of_trips

```