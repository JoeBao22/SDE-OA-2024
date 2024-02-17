# Job Execution
There are n jobs that can be executed in parallel on a processor, where the execution time of the ith job is *executionTime[i]*. To speed up execution, the following strategy is used.

In one operation, a job is chosen, the major job, and is executed for x seconds. All other jobs are executed for y seconds where y < x.

A job is complete when it has been executed for at least *executionTime[i]* seconds, then it exits the pool. Find the minimum number of operations in which the processor can completely execute all the jobs if run optimally.
### Example
Consider n = 5, executionTime = [3, 4, 1, 7, 6], x = 4 and y = 2.

The following strategy is optimal using 1-based indexing.

- Choose job 4 as the major job and reduce the execution times of job 4 by x = 4 and of other jobs by y = 2.
Now executionTime = [1, 2, -1, 3, 4]. Job 3 is complete, so it is removed.
-  Choose job 4, executionTime = [-1, 0, -, -1, 2]. So, jobs 1, 2, and 4 are now complete. -  Choose job 5, executionTime = [-, -, -, -, -27. Job 5 is complete.
It takes 3 operations to execute all the jobs so the answer is 3.

### Function Description
Complete the function *getMinimumOperations* in the editor below.
*getMinimumOperations* has the following
parameters:
- int execution Time[n]: the execution times of each job
- int x. the time for which the major job is executed
- int y. the time for which all other jobs are executed