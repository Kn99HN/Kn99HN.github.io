---
title: "Server Missing"
date: 2020-08-17T21:29:59-04:00
draft: false
---

# Server Missing

## Description
```
// Given an array of server ids as integers. Find the first free server
// Server ids start at 1
// >> find_free_server([]) # 1
// >> find_free_server([5, 1]) # 2
```

## Solution
We can approach this problem with a few different ones. First, we can sort the array, we can then check if the next one is available.

Second approach would be finding the maximum value in the array, we can then iterate from i up to the maximum value. The moment we find a number that is missing, we break and return.

Third, we can also use 2 pointers, we calculate the differences between 2 values. If the differences are greater than 1, we know there is a missing number in between them, we can then add 1 to the smaller value, and keep track of the missing value. We then keep checking and find the smallest missing value, that would be the next free server.

## Follow up
Creating a class that allows creating and deleting server name

### Takeaway
1. It's better to not blindly follow built in algorithm. Sometimes, it's easier to scan through the array and parse.
2. There is tradeoff when creating an API.
3. Focus on user friendly API and avoid redundancy.
4. Heap is useful since it's O(nlogn) and allows you to sort and delete quickly.

