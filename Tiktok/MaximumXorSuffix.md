# Maximum XOR Suffix

An array of n integers, *arr*, is given. Pick any index then calculate the XOR of the array from that index through the highest index. Append the value to the array. Repeat this process zero or more times. Determine the highest value possible.
### Example 
n = 5, arr = [8, 2, 4, 12, 1].
One way to achieve the maximum is shown. The symbol indicates the bitwise XOR operation.
Operation (0-indexed)
- Choose i = 4.  arr[5] = arr[4]. Result: [8, 2, 4, 12, 1, 1]
- Choose i = 1. arr[6] = arr[1] arr[2] ... → arr[5]. Result: [8, 2, 4, 12, 1, 1, 10]
- Choose i = 2. arr[7] = arr[2] arr[3] ... → arr[6]. Result: [8, 2, 4, 12, 1, 1, 10, 6]
- Choose i = 0. arr[8] = arr[0] arr[1] ... arr[7]. Result: [8, 2, 4, 12, 1, 1, 10, 6, 14]

The maximum strength possible is 14.

### Function Description
Complete the function *maximumValue* in the editor below.
*maximumValue* has the following parameter:
- int arr[n]: the starting array
### Return
int: the maximum possible value in the array
### Constraints
- $1 \leq n \leq 10^5$
- $0 \leq arr[i] \leq 2^{30}$

### Solution
**Analysis**

Actually I am not able to give a clean solution, just some rough ideas here.

- XOR is communicative and associative
- v XOR v = 0, v XOR 0 = v
- suppose i <= j <= k <= l, then :
1) (v_i ... v_n) 
2) (v_i ... v_n) XOR (v_j ... v_n) = v_i ... v_j
3) (v_i ... v_n) XOR (v_j ... v_n) XOR (v_k ... v_n)= (v_i ... v_j) XOR (v_k ... v_n)
4) (v_i ... v_n) XOR (v_j ... v_n) XOR (v_k ... v_n) XOR (v_l ... v_n ) = (v_i ... v_j) XOR (v_k ... v_l)

The closure of applying any number of operations is just a subsequence of the original array. I know that Trie can solve the problem for subarray XOR result, but I don't know what kind of algorithm can efficiently solve subsequence XOR result. Backtracking/dfs will work, but they probably don't satisfy the time requirement. 

TODO: add next step 
 
