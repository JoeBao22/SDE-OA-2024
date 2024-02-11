# Contiguous Subarray

You are given an array of integers numbers and a positive integer $k$. Your task is to count the number of contiguous subarrays within $numbers$ that contains at least $k$ pairs of elements with duplicate values.

More formally, count the number of contiguous subarrays $numbers [i..j]$ ($i \leq j$) for which there are $2 * k$ elements (with **pairwise distinct** indices $i \leq i_1, j_1, i_2, j_2, ...., i_k, j_k$) with each pair having same value  - $numbers [i_1] = numbers [j_1]$, $numbers [i_2] = numbers[j_2]$, ..., $numbers[i_k] = numbers[j_k]$



### Example

#### Example1
For numbers = [0, 1, 0, 1, 0] and k = 2, the
output should be solution (numbers, k) = 3. There are 3 subarrays that satisfy the criteria of containing at least k = 2 pairs of duplicate
values:

- numbers [0..3] = [0, 1, 0, 1] with numbers [0] = 0 = numbers [2] and numbers [1] = 1 = numbers [3]
- numbers [1..4] = [1, 0, 1, 0] with numbers [1] = 1 = numbers [3] and numbers [2] = numbers [4] = 0 
- numbers [0..4] = [0, 1, 0, 1, 0] with numbers [0] = 0 = numbers [2], numbers [1] = 1 = numbers [3], and numbers [2] = 0 = numbers [4].

In each of these subarrays, there is at least one pair of os and one pair of 1 s.

#### Example2 
For numbers = [2, 2, 2, 2, 2, 2] and k = 3,
the output should be solution (numbers, k) = 1.
There is only 1 applicable subarray
numbers [0..5] = [2, 2, 2, 2, 2, 2], which
contains at least 3 pairs of 2. 

### Solution

```Python
def ContigousSubarrayBruteForce(numbers, k):
    total_subarray = 0
    for i in range(len(numbers) - 2 * k + 1):
        for j in range(i+2 * k, len(numbers)):
            counter_dict = {}
            for idx in range(i, j):
                val = numbers[idx]
                counter_dict[val] = counter_dict.get(val, 0) + 1
            counter_pairs = 0
            for k, v in counter_dict.items():
                counter_pairs += v * (v-1) // 2
            if counter_pairs >= k:
                total_subarray += 1
    return total_subarray

```