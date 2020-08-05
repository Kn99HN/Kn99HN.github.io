---
title: "Word Break"
date: 2020-08-04T22:10:58-04:00
draft: true
---

# Word Break

## Description
Given a non-empty string s and a dictionary wordDict containing a list of non-empty words, determine if s can be segmented into a space-separated sequence of one or more dictionary words.

Note:

    The same word in the dictionary may be reused multiple times in the segmentation.
    You may assume the dictionary does not contain duplicate words.

```
Input: s = "leetcode", wordDict = ["leet", "code"]
Output: true
Explanation: Return true because "leetcode" can be segmented as "leet code".
```

## Solution
I found that many problem that involves string seems to have similar solutions. I was able to find the recursive function but I wasn't patient enough to come up with the DP-based solution. However, it is fairly straightforward

We know that if `s` in `wordDict` then the string can be segmented. We then check each index. If the accumulated string is in wordDict, we check if `s[i+1:]` is in wordDict. Then, if both are `True`, we know that current `s` can be segmented using `wordDict`. Then, we can add it to our `cache`, which is a dictionary with key is the current string `s`.

If we never satisfy the condition above, we return `False`.