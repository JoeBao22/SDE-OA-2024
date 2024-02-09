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
