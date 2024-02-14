# Sort Product Codes


Amazon has millions of products sold on its e-commerce website, and each product is identified by its product code.

Given an array of $n$ *productCodes* and order, a string that represents the precedence of characters, sort the *productCodes* in lexicographically increasing order per the precedence.

Note: Lexicographical order is defined in the following way. When we compare strings *s* and *t*, first we find the leftmost position with differing characters: *s*, *t*, If there is no such position (i. e. s is a prefix of t or vice versa) the shortest string is less. Otherwise, we compare characters *s*, and *t*, according to their order in the given precedence order.


### Example:

If n=2, order = "abcdefghijklmnopqrstuvwxyz", and productCodes is ["adc", "abc"], the sorted order is ["abc", "adc"]. 

Consider the strings "adc" and "abc", the first point of difference is at position 1 (assuming start index is 0), and 'd'>'b' according to the given precedence order.
### Function Description
Complete the function *sortProductCodes* in the editor below.
sortProductCodes has the following parameter(s): 
- string order. the new precedence order string 
- productCodes[n]: the array to sort 
### Returns
string[n]: the productCodes array in sorted order

### Constraints
- $ 1 \leq n \leq 5000 $
- $ 1 \leq$ length(productCodes[i]) $\leq 100$
- length(order) = 26
- order and all productCodes[i] contain lowercase English letters only.

### Solution
```Python
def sortProductCodes(order, productCodes):
    alphabet_order = "abcdefghijklmnopqrstuvwxyz"
    mapping = {}
    for char1, char2 in zip(order, alphabet_order):
        mapping[char1] = char2
    mapped_codes = []
    for i, code in enumerate(productCodes):
        mapped_code = ''.join([mapping[char] for char in code])
        mapped_codes.append((mapped_code, i))
    mapped_codes.sort()
    return [productCodes[i] for _, i in mapped_codes]
```
