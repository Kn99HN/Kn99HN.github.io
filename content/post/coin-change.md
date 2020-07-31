---
title: "Coin Change"
date: 2020-07-30T22:10:27-04:00
draft: false
---

# Coin Change

## Description
You are given coins of different denominations and a total amount of money amount. Write a function to compute the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.

```
Input: coins = [1, 2, 5], amount = 11
Output: 3 
Explanation: 11 = 5 + 5 + 1
```
## Solution
I was stuck on this problem for a bit since it's not really similar to others DP I have tackled. At first, I though we have a few options, we can take the current value and subtract it from `amount`. We then either do the same step or take the value at index `i-1`. However, it turns out that this is not the best solution we can have. 


The way to think about this is to use a nested for loop since we can have an infinite amount of coins to use. We recursively take the current value and subtract it from `amount`, passing it back into the function. Eventually, we will reach a point where `amount` becomes negative or 0, in which case, we can return. We then handle the edge cases to keep track of the minimum number of coins taken to add up to `amount`.

We then check if the `min_val` equals to `amount + 1`, meaning we have overcount the number of steps taken. Hence, we return `-1` since it is an invalid answer. Otherwise, we return `min_val`.

