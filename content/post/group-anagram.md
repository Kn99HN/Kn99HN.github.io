---
title: "Group Anagram"
date: 2020-09-15T22:57:21-04:00
draft: false
---

# Group Anagram
## Description
Given an array of strings strs, group the anagrams together. You can return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

```
Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
```

## Solution
This is a follow up or a bit harder problem than valid anagram. However, the approach is quite similar, we use a hashmap to store our values. As we iterate through th string,
we first sorted the word and use it as a key. If the word is in the hashmap, we update the list, otherwise we can initialize a list with the word. We will store the non-sorted
word.



