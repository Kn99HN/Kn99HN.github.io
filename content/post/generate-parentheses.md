---
title: "Generate Parentheses"
date: 2020-10-04T23:44:04-04:00
draft: false
---

# Generate Parantheses
## Description
Given n pairs of parentheses, write a function to generate all combinations of well-formed parentheses.

```
Input: n = 3
Output: ["((()))","(()())","(())()","()(())","()()()"]
```

## Solution
1. The most brute force way to do this is to generate all possible combination of the parantheses given n. We then check if it's valid or not then we can add it.

2. A better solution is to have a `max` counter. We have `start` and `end` indicating which parantheses to add to the string. Here are some cases:
- If `start < max`, we can keep adding `(`.
- If `close < start`, we will start adding `)`, indicating we can start forming a pair of valid paranthesis.
- If `string length == max * 2`, we can add it to the list. Otherwise, we keep repeating the process.

=> Backtrack problems

