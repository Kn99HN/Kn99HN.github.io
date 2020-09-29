---
title: "Top K Frequent Elements"
date: 2020-09-29T09:21:40-04:00
draft: false
---

# Top K Frequent Elements
## Description
Given a non-empty array of integers, return the k most frequent elements.

```
Input: nums = [1,1,1,2,2,3], k = 2
Output: [1,2]
```

1. You may assume k is always valid, 1 ≤ k ≤ number of unique elements.
2. Your algorithm's time complexity must be better than O(n log n), where n is the array's size.
3. It's guaranteed that the answer is unique, in other words the set of the top k frequent elements is unique.
4. You can return the answer in any order.

## Solution
There are certainly many approaches to the problem. I personally prefer thinking in sequential 
steps so mine will take O(n + k) space but runs in O(nlogk) where k is the number of unique elements
in the list.

First, we build the hashmap with key being the value at value being the number of its occurences. We
then create a heap with comparator based on the pair `(a,b)` where `a is the value` and `b is the occurences`.
We order the heap by the frequency, which is b. We then add all (key, value) pair into the heap.
We then poll/pop k times from the heap to get the k most frequent elements.

This will guarantee our code runs in O(nlogk).

