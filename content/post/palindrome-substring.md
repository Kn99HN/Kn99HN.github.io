---
title: "Palindrome Substring"
date: 2020-09-16T22:55:54-04:00
draft: false
---

# Palindrome Substring
Given a string, your task is to count how many palindromic substrings in this string.

The substrings with different start indexes or end indexes are counted as different substrings even they consist of same characters.

```
Input: "abc"
Output: 3
Explanation: Three palindromic strings: "a", "b", "c".
```

# Solution
The brute force solution is to break down the problem into checking for valid palindrome. We use 2 indices, and iterating them in a nested for loop, checking if each `s[start:end+1]` is a valid palindrome.

The more optimized version of this problem is that noticing a palindrome can also be checked from the middle point and not just the start and the end. So instead, we keep expanding from the middle of string to ensure that we have a valid palindrome. We have to keep count of `(i,i)` and `(i,i+1)`
because there are cases when the string length is even.

