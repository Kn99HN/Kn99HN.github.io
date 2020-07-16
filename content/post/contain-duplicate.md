---
title: "Contain Duplicate"
date: 2020-07-16T13:21:45-04:00
draft: false
---

# Contain Duplicates

## Description
Given an array of integers, find if the array contains any duplicates.

Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

```
Input: [1,2,3,1]
Output: true
```

## Solution
- Using a set, we add values if not already in the set and if it is already in the set,
it means that there are duplicates.
