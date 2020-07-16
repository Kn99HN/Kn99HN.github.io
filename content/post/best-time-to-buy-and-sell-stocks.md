---
title: "Best Time to Buy and Sell Stocks"
date: 2020-07-16T12:58:39-04:00
draft: false
---

Since it was so difficult to start leetcode. I think it will be better
if I document each problem that I solve every day.

# Best Time to Buy and Sell Stocks

## Description
Say you have an array for which the ith element is the price of a given stock on day i.

If you were only permitted to complete at most one transaction (i.e., buy one and sell one share of the stock), design an algorithm to find the maximum profit.

Note that you cannot sell a stock before you buy one.

```
Input: [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
             Not 7-1 = 6, as selling price needs to be larger than buying price.
```

## Solution
This is deemed as an easy question but I don't really think so when I was doing it
the first time. I choose a sliding window approach.

There are a few cases that a max profit can happen. But it boils down to this:
- If the value at the low pointer is greater than one at high pointer then
clearly it is not a maximum value. Hence, we skip all the values from low
up to high. If the max value existed between the low and high, it must
have been founded before. 
- Else, we take the difference and compare with max value.

The value at the end of the while loop is the maximum value.
