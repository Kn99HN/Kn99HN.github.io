---
title: "Course Schedule"
date: 2020-08-18T22:08:41-04:00
draft: false
---

# Course Schedule

## Description
There are a total of numCourses courses you have to take, labeled from 0 to numCourses-1.

Some courses may have prerequisites, for example to take course 0 you have to first take course 1, which is expressed as a pair: [0,1]

Given the total number of courses and a list of prerequisite pairs, is it possible for you to finish all courses?

```
Input: numCourses = 2, prerequisites = [[1,0]]
Output: true
Explanation: There are a total of 2 courses to take. To take course 1 you should have finished course 0. So it is possible.
```

## Solution
This is a topological sort problem. For some reasons, I was remembering the DFS implementation instead of a more straightforward solution, which relies on counting the number of indegree of a node.

We first count all the indegree in the graph. Then, we create a queue, adding nodes to it if there's an indegree of 0.

We then remove node from the queue as long as it's not empty, decreasing the indegree of each node. Once the indegree of the current node is 0, we add it to the queue again. At the end, if we have a list with same size as the number of courses, we know that the courses are valid. We are sure of this possibility because the graph should end up with the same number of node with an indegree of 0 at the end. Otherwise, there is a cycle in the graph



