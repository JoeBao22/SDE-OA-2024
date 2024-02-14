# String Search in Matrix
You are given a matrix of characters and an array of distinct strings words. Your task is to implement a simplified string search by determining the number of times in which strings from words can be found in the matrix under the following constraints:

- A string is found when it can be formed by
combining characters along some path in the matrix.
- A path may start at any cell, and initially must go from left to right or from top to bottom.
- All paths are allowed to change direction once to go in the opposite direction (i.e., from left -> right to right -> left, or from top -> bottom to bottom -> top).

Review the examples below for details.

Note: You are not expected to provide the most optimal solution, but a solution with time complexity not worse than o (matrix. length * matrix[0].length * words.length * (max (words [i].length)) will fit within the execution time limit.

### Example
- For
matrix = [["a", "b", "a", "c"],
["x", "a", "c", "d"],
["y", "r", "d", "s"]]
and words = ["ac", "cat", "car", "bar",
"acdc", "abacaba"], the output should be
solution (matrix, words) = 7
![Explanation](../img/Meta_WordSearchInMatrix.jpg)
### Solution
```Python
# The time complexity doesn't satisfy the requirement
def dfs(matrix, i, j, direction, word):
    if len(word) == 0:
        return True
    if i < 0 or i >= len(matrix) or j < 0 or j >= len(matrix[0]):
        return False
    if matrix[i][j] == word[0]:
        return dfs(matrix, i+direction[0], j+direction[1], direction, word[1:])
    return False


def StringSearchInMatrix(matrix, words):
    counter = 0
    for word in words:
        for split_idx in range(len(word)):
            # consider rev(word[0:i+1]) and word[i:]
            word1 = word[:split_idx+1][::-1]
            word2 = word[split_idx:]
            # from right to left, or from bottom to top
            for i in range(len(matrix)):
                for j in range(len(matrix[0])):
                    if dfs(matrix, i, j, (0, -1), word1) and dfs(matrix, i, j, (0, -1), word2):
                        counter += 1
                    if dfs(matrix, i, j, (-1, 0), word1) and dfs(matrix, i, j, (-1, 0), word2):
                        counter += 1
    return counter
```
