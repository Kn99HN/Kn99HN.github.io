---
title: "Longest Palindromic Substring"
date: 2020-09-17T22:58:04-04:00
draft: false
---

# Longest Palindromic Substring

## Description
Given a string s, find the longest palindromic substring in s. You may assume that the maximum length of s is 1000.

```
Input: "babad"
Output: "bab"
Note: "aba" is also a valid answer.
```

## Solution
This is a variation of the palindromic substring problem and valid palindrome string problem. What we do is create a helper function that expands and keep track of a valid palindrome. We then, at the end, return the string we found

Similarly to the palindromic substring problem, we iterate through the list and we expand from `(i,i)` and `(i,i+1)`. We then check for the maximum length between these to have a local longest substring and also then check with the global substring.


