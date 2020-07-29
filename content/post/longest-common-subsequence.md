---
title: "Longest Common Subsequence"
date: 2020-07-28T21:43:55-04:00
draft: false
---

# Longest Common Subsequence

## Description

Given two strings text1 and text2, return the length of their longest common subsequence.

A subsequence of a string is a new string generated from the original string with some characters(can be none) deleted without changing the relative order of the remaining characters. (eg, "ace" is a subsequence of "abcde" while "aec" is not). A common subsequence of two strings is a subsequence that is common to both strings.

 

If there is no common subsequence, return 0.

```
Input: text1 = "abcde", text2 = "ace" 
Output: 3  
Explanation: The longest common subsequence is "ace" and its length is 3.
```

## Solution
I used to be scared of most DP problem as I can't really find any pattern to start with. Though after Dr. Shoup's algorithm class, I do have a better sense of what to do.

I like to use the most straightforward approach, which is to find the brute force solution using recursion or others and then memoization. For this problem, we want to find the longest common substring given `text1` and `text2`.

Given two pointers, we have a two options:
- If the char at 2 pointers are similar, we move forward with an incremented counter. The 2 pointers are also incremented.
- If the char is not the same, we can either move the first pointer forward or the second pointer forward. In this case, we take the max value from the 2 values received.

Though we have solved the problem for shorter strings. Given a longer string, the algorithm will time out. Hence, memoization kicks in. We store the value in a 2D array, `cache`. At each step, we store in `cache[i][j]` the value returned from our recursive option above. Hence, the next time we call the helper function, we just have to check if `cache[i][j]` is not -1, indicating that the value has already been computed.
