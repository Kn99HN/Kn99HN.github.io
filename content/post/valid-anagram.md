---
title: "Valid Anagram"
date: 2020-09-14T22:44:40-04:00
draft: false
---

# Valid Anagram
Given two strings s and t , write a function to determine if t is an anagram of s.

```
Input: s = "anagram", t = "nagaram"
Output: true
```

# Solution
There are couple of ways we can solve this problem. We can use built-in `sorted` function and sort both strings, we then just need to compare if 2 strings are the same after sorting. This will take O(n*log(n)).

Another solution is to use hash table or an array with length 26, since there are 26 alphabet characters. We can compute the index by using the ascii code conversion function `ord`. We then iterate through first string to populate the cache, then through the second string to `pop` the cache. At the end, if the cache is empty, it will be True
