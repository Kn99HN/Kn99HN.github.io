---
title: "Sum Root to Leaf Numbers"
date: 2020-09-28T12:22:52-04:00
draft: false
---

# Sum Root to Leaf Numbers
## Description
Given a binary tree containing digits from 0-9 only, each root-to-leaf path could represent a number.

An example is the root-to-leaf path 1->2->3 which represents the number 123.

Find the total sum of all root-to-leaf numbers.

Note: A leaf is a node with no children.
```
Input: [1,2,3]
    1
   / \
  2   3
Output: 25
Explanation:
The root-to-leaf path 1->2 represents the number 12.
The root-to-leaf path 1->3 represents the number 13.
Therefore, sum = 12 + 13 = 25.
```

## Solution
We know that we would need to traverse from root node to the last node in order
to find the number in its final form. Hence, we create list to store all the possible
numbers from root to leaf. We know that if the current node is a leaf, we can add
the number to the list. Otherwise, we continue recursing.

At the end, we traverse the list for the sum and return it

