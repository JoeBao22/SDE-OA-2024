# Find Recurring Names
Amazon rewards its new users with a discount coupon that can be applied to their first purchase. Some users create more than one account in order to receive the offer multiple times. It was found that their new usernames are only a permutation of their real names.

For examples, if the real usernames of the users are realNames = ["abc", "def"] and the list of all usernames is allNames = ["bca", "abc", "cba", "def"], then the user "abc" must have made multiple accounts as there are three permutations of "abc" in the list of all usernames.

Given an array of realNames an array allNames of usernames for each account, identify the names of users who created accounts more than once. The goal is to return the array of real names of these users in lexicographical order. If there are no such names, return an array containing only the string "None".

Please note that:
- It is guaranteed that no two real names are permutations of each other. For the variable realNames, each value is unique, and indicates an individual person.
- Each name in allNames is a permutation of some name in realNames.
- There may be some names in realNames without a permutation in allNames.
- It is possible that some users may create an account using fake names only.

### Example
For example, the length of *realNames* n=3 and the length of *allNames* m=5.

realNames = ["alice", "bob", "terry"]

allNames = ["celia", "alice", "retry", "bob", "terry"]

A permutation of "alice" occurs twice in allNames as "alice" and "celia".

A permutation of "bob" occurs once.

A permutation of "terry" occurs twice as "terry" and "retry".

The real names with more than one occurrence in allNames are "alice" and "terry". Return them in lexicographical order, ["alice", "terry"].


Notes: Lexicographical order is ordering strings in the dictionary or alphabetical order. For example, string "hacker" comes before string "rank" in lexicographical order.
A permutation of a string is another string that contains the same characters, only the order of characters can be different.
### Function Description
Complete the function *findRecurringNames* in the editor below.
*findRecurringNames* has the following parameters:
- string realNames[n]: the real user names
- string allNames[m]: all registered user names
### Returns
- string[] the distinct real names of users with multiple registrations in lexicographical order
### Constraints
- $1 \leq n, m<10^5$
- $1 \leq |realNames[i]|, |allNames[i]| \leq 10$
- Each name in realNames and allNames consists of lowercase English letters only.


### Solution
```Python
def FindRecurringNames(realNames, allNames):
    sorted_real_names = []
    sorted_to_original = {}
    for real_name in realNames:
        sorted_real_name = "".join(sorted(real_name))
        sorted_real_names.append()
        sorted_to_original[sorted_real_name] = real_name
    sorted_to_counter = {}
    for name in allNames:
        sorted_name = "".join(sorted(real_names))
        sorted_to_counter[sorted_name] += 1
    recurring_names = []
    for sorted_name, value in allNames:
        if value >= 2:
            original_name = sorted_to_original[sorted_name]
            recurring_names.append(original)
    recurring_names.sort()
    return recurring_names

    
```