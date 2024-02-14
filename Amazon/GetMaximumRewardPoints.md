# GetMaximumRewardPoints
Amazon Shopping periodically has offers to attract more customers.

It recently launched an offer for n items in its inventory, where the $i^{th}$ item offered $reward[i]$ reward points to the customer purchasing the item. Every time an offer-bearing item is purchased, the customer gains the reward points associated with that item. Then the reward points of the remaining items are reduced by 1 unless it will reduce the points below 0.

Find the maximum possible reward points that can be gathered by purchasing the items optimally.

Note: Each item can be purchased at most once, in other words, $reward[i]$ becomes 0 after the ith item is purchased.

### Example
Consider the number of items to be $n = 5$, and their reward points to be $reward = [5, 2, 2, 3, 1]$. The items can be purchased as follows:

Considering 0-based indexing, the items can be purchased in the following order:
- First, purchase item 2, points earned = reward[2] = 2. Points of remaining items after this purchase reward = [4, 1, 0, 2, 0].
- Next, purchase item 3, points earned = reward[3] = 2. Points of remaining items after this purchase reward = [3, 0, 0, 0, 0].
- Finally, purchase item 0, points earned = reward[0]= 3. Points of remaining items after this purchase reward = [0, 0, 0, 0, 0].
- At this point, no items have reward points left. The maximum reward points is 2+2+3=7.

### Function Description 

Complete the function *getMaximumRewardPoints* in the editor below.

*getMaximumRewardPoints* has the following parameter(s):

- int reward[n]: the reward points of each item

### Returns
- long_int: the maximum reward points which can be collected.

### Constraints
- $1 \leq n \leq 10^5$
- $ 0 \leq rewards[i] \leq 10^6$