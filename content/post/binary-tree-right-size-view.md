---
title: "Binary Tree Right Size View"
date: 2020-10-05T23:55:49-04:00
draft: false
---

# Binary Tree Right Size
## Description
Given a binary tree, imagine yourself standing on the right side of it, return the values of the nodes you can see ordered from top to bottom.

```
Input: [1,2,3,null,5,null,4]
Output: [1, 3, 4]
Explanation:

   1            <---
 /   \
2     3         <---
 \     \
  5     4       <---
```

## Solution
We notice that it is similar to a branching problem, i.e BFS, and select the last element of each BFS exploration. We use a queue to implement BFS. Within our BFS, we iterate each level, popping an element at a time.

We then select the last value from the current level, indicating that's our right side view.

=> Breadth First Search


