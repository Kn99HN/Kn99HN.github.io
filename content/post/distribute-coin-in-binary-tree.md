---
title: "Distribute Coin in Binary Tree"
date: 2020-11-15T23:03:13-05:00
draft: false
---

# Distribute Coin in Binary Tree
## Description
Given the root of a binary tree with N nodes, each node in the tree has node.val coins, and there are N coins total.

In one move, we may choose two adjacent nodes and move one coin from one node to another.  (The move may be from parent to child, or from child to parent.)

Return the number of moves required to make every node have exactly one coin.

## Solution
- The approach is similar to a simulation. We know the number of coins is `<=` the number of nodes in the tree.
- At each node, they must contain at most 1 coins and no 0 coin.
- Hence, we recursively solve left and right subtree.
- Each step, we take 1 coin, pass down node.val - 1 coins and add them up to return
- Hence, the total number of `steps = Abs(# of ways on left) + Abs(# of ways on right)`.
- If we have a negative value, it indicates that we must need a coin, if it's positive, that's the extra
- So, we return `root.val + L + R - 1`
