---
title: "Longest Repeating Char Replacement"
date: 2020-09-11T13:17:34-04:00
draft: false
---

# Longest Repeating Character Replacement

## Description
Given a string s that consists of only uppercase English letters, you can perform at most k operations on that string.

In one operation, you can choose any character of the string and change it to any other uppercase English character.

Find the length of the longest sub-string containing all repeating letters you can get after performing the above operations.

Note:
Both the string's length and k will not exceed 104.

```
Input:
s = "ABAB", k = 2

Output:
4

Explanation:
Replace the two 'A's with two 'B's or vice versa.
```

```
Input:
s = "AABABBA", k = 1

Output:
4

Explanation:
Replace the one 'A' in the middle with 'B' and form "AABBBBA".
The substring "BBBB" has the longest repeating letters, which is 4.
```

## Solution
This is a sliding window problem. I did not have lots of practice with these kind of problem so I struggle a little bit at the very beginning. At first, I break this problem down as at each starting point, find out the maximum substring with repeating character. However, I was quite wrong.

The approach to the problem is to always keep a window with size k + most_frequent_character.

So we first initialize an array of char with 26 slots, which hold the alphabet letter. We then iterate through the string.
We increment at each char in the array. We then find the max of current local max or current count for the current character.

Next, we have to check whether our sliding windown in range with the formula `right - left - most_frequent + 1 > k`. The formula makes sense because we want to choose character with the minimum appearance to change it. Hence, that number must be `<= k`. Therefore, if it is not, we shrink our windown size from the left, i.e decrement in the char array and increment `left` value.

We then take the max of local and global max value. Then return it!


