# Find Maximum Num
Your team at Amazon is building a quiz-style application to help students prepare for certification exams. Each quiz module tests one or more subjects and limits the number of answers students can provide. You have been asked to examine the impact of this limit on the ability of students to "pass" certain subjects within quiz modules. To do this, please review and solve for the following: Imagine a student has already answered $answered[i]$ questions in each of the the th subjects, and still has time to answer a total of q more questions overall. For each th subject, the number of questions answered has to be at least $needed[i]$ in order to pass.

Determine the maximum number of subiects the student can pass if the $q$ additional answered questions are optimally distributed among the subjects.

### Example
For example, consider that there are n = 2
subjects and needed = [4, 5] answered questions,
respectively, to pass. Imagine the student has
answered answered = [2, 4] questions in the two
subjects so far, and can answer another q = 1 questions across all subjects combined. In that case, the best outcome is to answer an additional question in the second subject, in order to pass it, as 2 more answers are required to pass the first subject. The maximum number of subjects that can be passed is 1.

### Solution
```python

def findMaximumNum(answered, needed, q):
    diff = [max(0, needed[i] - answered[i]) for i in range(len(answered))]
    diff.sort()
    idx = 0
    while True:
        if q >= diff[idx]:
            q -= diff[idx]
            idx += 1
        else:
            break
    return idx
```