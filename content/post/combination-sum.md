---
title: "Combination Sum"
date: 2020-10-03T14:39:34-04:00
draft: false
---

# Combination Sum

## Description
Given an array of distinct integers candidates and a target integer target, return a list of all unique combinations of candidates where the chosen numbers sum to target. You may return the combinations in any order.

The same number may be chosen from candidates an unlimited number of times. Two combinations are unique if the frequency of at least one of the chosen numbers is different.

It is guaranteed that the number of unique combinations that sum up to target is less than 150 combinations for the given input.

```
Input: candidates = [2,3,6,7], target = 7
Output: [[2,2,3],[7]]
Explanation:
2 and 3 are candidates, and 2 + 2 + 3 = 7. Note that 2 can be used multiple times.
7 is a candidate, and 7 = 7.
These are the only two combinations.
```

## Solution
This is a really good example of a recursive problem, which I really enjoy. It is also a backtrack problem. 

Our base case:
1. If target == 0, we would like to add the combination to the bigger one. However, we need to create a deep copy to avoid modifying the state of it.
2. If target < 0 or i < 0, we don't really care
3. If target < `candidates[i]`, we would like to keep searching at `i - 1` instead.
4. Otherwise, we have 2 recursive calls:
- First, we add `candidates[i]` to the list, and recursively subtracting `candidates[i]` from it and not moving away fron the current index.
- After finishing the first recursive call, we remove the latest elements from the list since we know that if the first fails, it means the last value we have is invalid. So we remove it and moving our index to the left by 1.