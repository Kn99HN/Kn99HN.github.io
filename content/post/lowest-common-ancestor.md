---
title: "Lowest Common Ancestor"
date: 2020-09-29T09:17:43-04:00
draft: false
---

# Lowest Common Ancestor in BST
## Description
Given a binary search tree (BST), find the lowest common ancestor (LCA) of two given nodes in the BST.

According to the definition of LCA on Wikipedia: “The lowest common ancestor is defined between two nodes p and q as the lowest node in T that has both p and q as descendants (where we allow a node to be a descendant of itself).”

Given binary search tree:  root = [6,2,8,0,4,7,9,null,null,3,5]

```
Input: root = [6,2,8,0,4,7,9,null,null,3,5], p = 2, q = 4
Output: 2
Explanation: The LCA of nodes 2 and 4 is 2, since a node can be a descendant of itself according to the LCA definition.
```

## Solution
To be honest, I was stumped at the problem for a while and avoided it like COVID19. However,
after taking a quick look at it, I found that it is not bad at all!

We notice that the common ancestor will change if p and q are both less than current root or both
greater than the current root. If that's the case, the lowest common ancestor must be in either
the left or right subtree. Hence, we use a dummy `ancestorNode` to record the value each time.
Since the tree is a BST, we can apply the properties. We will only recurse on the left
and update `ancestorNode` iff both `p and q` < `current node`. Otherwise, we will move to the
right subtree and update `ancestorNode` with the immediate right node. If `current node = p` or
`current node = q`, we can just stop the recursion from going further.

