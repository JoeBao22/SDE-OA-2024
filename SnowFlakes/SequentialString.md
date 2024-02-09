# Sequential String 
A special string $s$ of length $n$ consists of characters 0-9 only. Its characters can only be accessed sequentially i.e the first '1' chosen is the leftmost '1' in s. There is an array arr of m strings, also consisting of characters 0-9. Calculate the minimum number of characters needed from sto construct a permutation of each of the strings in arr. 

Return an array of integers where the $i^{th}$ element denotes the minimum length of a substring that contains a permutation of the ith string in arr. If a string cannot be constructed, return -1 at that index. 


### Example
Consider n= 12, s= "064819848398", m= 3, arr= ["088", "364", "071]
- To construct "088", Alice needs to access the first 7 characters ("064819848398") of the special string and use only '0', '8', and '8'. Since the characters can be rearranged, the results for '088', '808', and '880' are all 7. 
- To construct "364", access the first 10 characters ("064819848398") of the special string and use only '6', '4', and '3'. Rearrange to match "364". 
- String "07" cannot be constructed from the special string. No '7' is available. 


The return array is [7, 10, -1]. Note that only bolded characters are used to construct the strings. 
### Function Description 
Complete the function $countMinimumCharacters$ in the editor below. 
$countMinimumCharacters$ has the following parameters: 
- string $s$: the special string of length n 
- string $arr[m]$: strings to construct 
### Returns 
- int[]: the ith element corresponds to the minimum number of characters required to construct the ith string, or -1 if the string cannot be constructed 
### Constraints
- $1 \leq n \leq 10^5$ 
- $1 \leq q \leq 2*10^4$
- $1 \leq$ sum of the lengths of strings in $arr \leq 5*10^5$ 
- All strings consist of characters '0'-'9' only. 

### Soluton: 
```python
def countMinimumCharacters(s, arr):
    min_counters = []
    for target_str in arr:
        index_target = 0
        index_s = 0
        while index_s < len(s):
            if s[index_s] == target_str[index_target]:
                index_target += 1
                index_s += 1
                if index_target == len(target_str):
                    # fully matched
                    min_counter.append(index_s)
                    break
            else:
                index_s += 1
        if index_target != len(target_str):
            min_counter.append(-1)
    return min_counters

```