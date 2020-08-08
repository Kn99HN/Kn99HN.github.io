---
title: "Decode Ways"
date: 2020-08-07T22:35:40-04:00
draft: false
---

# Decode Ways

## Description
A message containing letters from A-Z is being encoded to numbers using the following mapping:

```'A' -> 1
'B' -> 2
...
'Z' -> 26
```

Given a non-empty string containing only digits, determine the total number of ways to decode it.

```Example 1:

Input: "12"
Output: 2
Explanation: It could be decoded as "AB" (1 2) or "L" (12).
```

```Example 2:

Input: "226"
Output: 3
Explanation: It could be decoded as "BZ" (2 26), "VF" (22 6), or "BBF" (2 2 6).
```

## Solution
For this problem, we can think similar to fibonacci sequence. We have a range of number that is valid, which is from 1 to 26. We keep track of the current sequence using a string, `seq`. 

For each index, we have 2 choices, either move to the next value in the string, keeping the current sequence or move 2 steps ahead, changing the sequence as a pair of current index and next index. 

We have a base case such that:
- If current sequence is not in the mapping, it is not a valid decode. So we return 0.
- Otherwise, if we reach the end, it indicates that we must have a valid decoding before. Hence, we return 1.

We repeat this and use a dictionary as a memoization space. Then, at the end, we will get the total number of ways to decode the string.
