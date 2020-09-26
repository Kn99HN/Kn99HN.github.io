---
title: "Partition Labels"
date: 2020-09-26T17:28:45-04:00
draft: false
---

# Partition Labels

## Description
A string S of lowercase English letters is given. We want to partition this string into as many parts as possible so that each letter appears in at most one part, and return a list of integers representing the size of these parts.

```
Input: S = "ababcbacadefegdehijhklij"
Output: [9,7,8]
Explanation:
The partition is "ababcbaca", "defegde", "hijhklij".
This is a partition so that each letter appears in at most one part.
A partition like "ababcbacadefegde", "hijhklij" is incorrect, because it splits S into less parts.
```

## Solution
So we notice that there is a condition on our partition. We know that each partition must contain all the occurrence
of the characters. We notice that we can use a hashmap or an array to keep track of the last appearance of
the characters in question. After creating the map, we can iterate through the string again
and get the maximum value for j, which is the last index where our current char appears.

Then, in the case that i == j, we know that means we have reached the last possible occurence. Therefore,
we add it to the output array.

Another perspective on the problem can be similar to merge interval. We create a 2D array, which has
a pair of values with the index of where the character start and end. We then merge them using similar
solution as merge interval
