---
title: "Subsets"
date: 2020-10-21T22:18:00-04:00
draft: false
---

# Subsets
## Description
Given a collection of integers that contains unique nums, return all possible subsets (the power set).

Note: The solution set must not contain duplicate subsets.

```
Input: [1,2,3]
Output:
[
  [1],
  [2],
  [3],
  [1,2], [2,3], [1,3]
  [1,2,3]
  []
]
```

## Solution
If all integers are unique, this is a bactracking problem, we start at each index. We then will add the current value to the current array list, we then bactrack/recurse on the current index. At the end of the recursion, we remove the latest values.

### Follow up
- What if the array contains duplicates?

In this scenario, we can brute force by using the API and check if the current list contains that values.

Or

We can sort the array and check if `val(i) == val(i - 1)`. If so, continue. Otherwise, proceed to backtrack.


