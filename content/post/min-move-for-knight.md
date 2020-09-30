---
title: "Min Move for Knight"
date: 2020-09-30T12:43:42-04:00
draft: false
---

# Minimum Move For A Knight

## Description
In a finite chess board with coordinates, a knight start an index `startRow, startCol`.

A knight has 8 possible moves it can make, as illustrated below. Each move is two squares in a cardinal direction, then one square in an orthogonal direction.

Return the minimum number of steps needed to move the knight to the square [x, y].  It is guaranteed the answer exists.

```
Input: x = 2, y = 1
Output: 1
Explanation: [0, 0] → [2, 1]
```

## Solution
This was certainly a difficult problem. At first, I thought it's gonna be a DFS solution. However, after taking
a better look at this, there are 8 possible outcomes for each round of the knight. Instead of finding a path, we
are exploring ALL paths. Hence, it also looks similar to BFS(trying all possible paths) until we reach the 
destination.

Hence, we create a `Node` class with 3 fields `x,y,dist`. `dist` is to keep track of the distance between
the current `x and y` from the original position. We then create a queue, which I learn that Python supports
with `deque`. We implement a BFS with the queue. If the latest popped node match the destination, we return
the `dist`. Otherwise, we iterate through all the combination of steps and append them to the queue if they
are not already visited with `dist + 1`. Through this implementation, we are able to test all the possible
combinations and find the minimum distance.
