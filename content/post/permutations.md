---
title: "Permutations"
date: 2020-10-21T21:53:30-04:00
draft: false
---

# Permutations
## Description
Given a collection of distinct integers, return all possible permutations

```
Input: [1,2,3]
Output:
[
  [1,2,3],
  [1,3,2],
  [2,1,3],
  [2,3,1],
  [3,1,2],
  [3,2,1]
]
```

## Solution
This is a backtracking problem, which is actually quite difficult to think about but not that difficult. I think I need to get rid of the specific framwork for backtracking. Throughout the process, I was thinking about the subset problems, which is a wrong way.

3 Key values of a backtracking problems:
- Our choice in the recursion function
- Our contraints
- Our goal

The mental model is:
- We first choose the first value
- We have n - 1 values left
- We recursively choose from n - 1

In this particular problem, we iterate from an index and continously swapping them. We then backtrack/recurse on the current index. By the end of the recursion, we re-swap the value.



