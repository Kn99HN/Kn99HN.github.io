---
title: "Merge Intervals"
date: 2020-09-03T14:26:18-04:00
draft: false
---

# Merge Intervals

## Description
Given a collection of intervals, merge all overlapping intervals.

```
Input: intervals = [[1,3],[2,6],[8,10],[15,18]]
Output: [[1,6],[8,10],[15,18]]
Explanation: Since intervals [1,3] and [2,6] overlaps, merge them into [1,6].
```

## Solution
We notice that the first value of each interval is always less than the second value. We create a new array storing all of our merged intervals

We proceed to sort the array based on the first value of each interval. For each pair of value, we have 2 options: overllapping interval and non-overlapping interval. 

For the case of non-overlapping interval, we can add it immediately to the new array. Before that, we do have to check if the second value of the last interval in the new array is less than the first value at the current interval of the sorted array. If so, it is non-overlapping

For overlapping interval, we modify the second value of the latest interval in the new array. We change it to be the maximum value of the second value of the latest interval the new array and the second value of the current interval in the sorted array.



