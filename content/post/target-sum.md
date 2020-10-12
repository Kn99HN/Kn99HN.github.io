---
title: "Target Sum"
date: 2020-10-11T13:13:47-04:00
draft: true
---

# Target Sum
## Description
You are given a list of non-negative integers, a1, a2, ..., an, and a target, S. Now you have 2 symbols + and -. For each integer, you should choose one from + and - as its new symbol.

Find out how many ways to assign symbols to make sum of integers equal to target S.

```
Input: nums is [1, 1, 1, 1, 1], S is 3. 
Output: 5
Explanation: 

-1+1+1+1+1 = 3
+1-1+1+1+1 = 3
+1+1-1+1+1 = 3
+1+1+1-1+1 = 3
+1+1+1+1-1 = 3

There are 5 ways to assign symbols to make the sum of nums be target 3.
```

## Solution
This is very similar to subset sum problem in Shoup's class. I was able to deduce a brute force with DFS with O(2^n).

We first identify our base case:
1. If index is out of bound and current sum == target sum -> we increment the counter/return 1
2. If index is out of bound, we return 0.

At each step, if the `index < length of the array`, we recurse on 2 values, `sum + nums[index]` and `sum - nums[index]`. We then have 2 counter for adding and subtracting the current value. We then add and return them.

We identify the repeated subproblem in this case and memoize. I prefer using a hashmap in this case. We then use `(index, sum)` as our key and memorize the counter. If `(index, sum)` is in our hashmap/dictionary, we can return it.