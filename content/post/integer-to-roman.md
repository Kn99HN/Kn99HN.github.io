---
title: "Integer to Roman"
date: 2020-10-02T08:47:17-04:00
draft: false
---

# Integer to Roman
## Description
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

```
Input: 3
Output: "III"
```

## Solution
* Note: Try to solve the problem how it would intuitively solve in your head -> Simulate that solution!

We will find the greatest lower bound for our current number and then continuously subtract it from our current value. We then can eventually keep adding Roman Numeral to our output. 

We also don't have to keep finding the next lower bound. Rather, we can decrement counter one by one. Eventually, we will find the next greatest lower bound for our new number.

* Greedy Algorithm, taking most out of the current solution

