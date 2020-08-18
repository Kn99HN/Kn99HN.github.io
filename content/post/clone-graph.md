---
title: "Clone Graph"
date: 2020-08-17T21:26:14-04:00
draft: false
---

# Clone Graph

## Description

Given a reference of a node in a connected undirected graph.

Return a deep copy (clone) of the graph.

Each node in the graph contains a val (int) and a list (List[Node]) of its neighbors.

## Solution

This problem is not too bad since I have been doing this in Java a lot. So a graph is connected using an adjacency list. Hence, the best way to work through/traverse the whole graph is DFS by recursively searching through each node in the adjacency list.

At each step, we create a new Node, we then check its neighbors and recurse on the neighbors. I like to use a dictionary to keep track of the already created one. By doing so, we can get references of these nodes but if there are changes, we are still able to track them. 

