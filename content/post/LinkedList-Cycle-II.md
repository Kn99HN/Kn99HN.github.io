---
title: "LinkedList Cycle II"
date: 2020-10-27T11:37:02-04:00
draft: false
---

# LinkedList Cycle II
## Description
Given a linked list, return the node where the cycle begins. If there is no cycle, return null.

There is a cycle in a linked list if there is some node in the list that can be reached again by continuously following the next pointer. Internally, pos is used to denote the index of the node that tail's next pointer is connected to. Note that pos is not passed as a parameter.

Notice that you should not modify the linked list.

Follow up:

Can you solve it using O(1) (i.e. constant) memory?

```
Input: head = [3,2,0,-4], pos = 1
Output: tail connects to node index 1
Explanation: There is a cycle in the linked list, where tail connects to the second node.
```

## Solution
A naive approach is using set or hash table to keep track of visited node.

A better approach is to use Floyd's algorithm for finding intersection points. We have 2 pointers, 1 slow and 1 fast. Fast pointer is moving twice as fast as slow. Eventually, if they meet, that's the intersection point. If not, either one will go to null, indicating there is no cycle.

Once the intersection point is found, we learn that if we slow down both slow and fast pointers, we will be able to find the cycled point.

