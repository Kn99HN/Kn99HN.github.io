---
title: "Kth Smallest Element in BST"
date: 2020-09-28T12:20:44-04:00
draft: false
---

# Kth Smallest Element in BST
## Description
Given a binary search tree, write a function kthSmallest to find the kth smallest element in it.

## Solution
For this problem, we know that our input is a BST. Hence, if we traverse in order we will be able
to construct a list in increasing order. Therefore, we create a list and traverse the tree in order,
adding the node value at each point. We then return value at index `k-1`

