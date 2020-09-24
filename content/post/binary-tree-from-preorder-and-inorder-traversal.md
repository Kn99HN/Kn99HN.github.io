---
title: "Binary Tree From Preorder and Inorder Traversal"
date: 2020-09-24T13:00:45-04:00
draft: false
---

# Construct Binary Tree from Preorder and Inorder Traversal
## Description
Given preorder and inorder traversal of a tree, construct the binary tree.

Note:
You may assume that duplicates do not exist in the tree.

For example, given:
```
preorder = [3,9,20,15,7]
inorder = [9,3,15,20,7]
```

## Solution
This is quite a tricky problem. However, if we notice that there is a corresponding
between the 2 array, we can see that it is quite similar to merge sort but with
extra steps to take. We use recursion for this problem, we notice that the index `i`
at which `preorder[i] = inorder[i]` is where the tree split happen. All nodes from 
0 to `i - 1` is on the left subtree of node at `i` and the other is on the right subtree.

Then, we can do a recursion using 3 values: `low`, `high`, and `root_index`. `low` and `high`
handles the length of our subarray and `root_index` takes care of the split node.

So, we have a few cases to consider:
1, If `low=high`, then return the node at `low`
2, If `low > high`, then return `None`
3, If `low`, `high` or `root_index` falls out of range, return `None`
4, Else, we find the index in inorder array that matches with the value of `preorder[root_index]`.
We record this index and we recursively call the function using this index. We have:
- On our left, `low` is still the same, `high` is now `index - 1`, `root_index = root_index + 1`
- On our right, `low` is now `index + 1`, `high` is the same, and we notice that the `root_index` 
for the right subtree is as follows: `root_index = root_index + index - low + 1`.

We then have built our helper function to build the tree


