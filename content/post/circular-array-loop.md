---
title: "Circular Array Loop"
date: 2020-10-08T20:20:31-04:00
draft: false
---

# Circular Array Loop
## Description
You are given a circular array nums of positive and negative integers. If a number k at an index is positive, then move forward k steps. Conversely, if it's negative (-k), move backward k steps. Since the array is circular, you may assume that the last element's next element is the first element, and the first element's previous element is the last element.

Determine if there is a loop (or a cycle) in nums. A cycle must start and end at the same index and the cycle's length > 1. Furthermore, movements in a cycle must all follow a single direction. In other words, a cycle must not consist of both forward and backward movements.

```
Input: [2,-1,1,2,2]
Output: true
Explanation: There is a cycle, from index 0 -> 2 -> 3 -> 0. The cycle's length is 3.
```

## Solution
This is quite similar to detecting cycle in graph. There are a few solutions that we can approach:
1. We change our list into a graph, i.e adjency matrix, and then find the one with a cycle.
2. We can use full DFS, i.e bell and whistle, but only with a bell, which is the colors array to indicate whether or not the node has been visited

