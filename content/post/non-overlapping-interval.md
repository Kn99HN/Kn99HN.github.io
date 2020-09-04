---
title: "Non Overlapping Interval"
date: 2020-09-03T21:58:05-04:00
draft: false
---

# Non Overlapping Interval

## Description
Given a collection of intervals, find the minimum number of intervals you need to remove to make the rest of the intervals non-overlapping.

```
Input: [[1,2],[2,3],[3,4],[1,3]]
Output: 1
Explanation: [1,3] can be removed and the rest of intervals are non-overlapping.
```

```
Input: [[1,2],[1,2],[1,2]]
Output: 2
Explanation: You need to remove two [1,2] to make the rest of intervals non-overlapping.
```

## Solution
This is similar to merge intervals problem. At first, it seems a bit random how to approach this. However, after doing merge intervals problem, it becomes a lot easier to noice a pattern.

We first sort the intervals based on the last value in ascending order. Though we are finding the min number of interval to be removed, we can actually solve the contrary problem, which is finding the maximum non-overlapping interval.

Therefore, we can use a counter to keep track of the non-overlapping intervals. At the end, we can return `len(intervals) - counter` as that will be our minimum intervals to be removed

