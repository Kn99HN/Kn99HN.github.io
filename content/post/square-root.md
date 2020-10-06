---
title: "Square Root"
date: 2020-10-05T23:25:54-04:00
draft: false
---

# Square Root
## Description
Implement int sqrt(int x).

Compute and return the square root of x, where x is guaranteed to be a non-negative integer.

Since the return type is an integer, the decimal digits are truncated and only the integer part of the result is returned.

```
Input: 4
Output: 2
```

## Solution
Interestingly, we can use binary search to find the square root. We know that the square root of value `< (x / 2)`. We can then keep our range from `2` to `x/2`. We can keep comparing our current value with x and move our pivot, similar to a binary search. Eventually, we can find a number `=` to x, or arrive at the round-down value.
