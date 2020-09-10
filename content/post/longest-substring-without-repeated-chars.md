---
title: "Longest Substring Without Repeated Chars"
date: 2020-09-09T21:39:18-04:00
draft: false
---

# Longest Substring Without Repeated Character

## Description
Given a string s, find the length of the longest substring without repeating characters.

```
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

## Solution
We first breakdown the problem. We know that for each unique substring,
if the current value is duplicate the the cached substring, the maximum
index of the last char in that substring must be `<=` to the current index/char.

Therefore, at each time, we just need to check if the `s[curr]` in hashmap/dict,
if so, retrieve the index + 1, that will be our starting index of the new unique substring.
Hence, we just need to find the max between current max and `i-start+1`. We then update
the dict with new key-value. This can be thought of as sliding-window!