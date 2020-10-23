---
title: "Find First and Last Position"
date: 2020-10-23T12:40:29-04:00
draft: false
---

# Find First and Last Position in Sorted Array
Given an array of integers nums sorted in ascending order, find the starting and ending position of a given target value.

If target is not found in the array, return [-1, -1].

Follow up: Could you write an algorithm with O(log n) runtime complexity?

```
Input: nums = [5,7,7,8,8,10], target = 8
Output: [3,4]
```

## Solution
### Naive Approach
- Use a `hashmap<Integer, List<Integer>>`, the value is the indices at which the last values occurs. 
- Scan through the array and keep updating the map.
- If target is in the map, find its start and last indices. If not return `[-1,-1]`.

## Modified Binary Search
- Modifying binary search for our purposes.
- We will find the left and right indices separately.
- For left, if the `mid == target`, we move high toward mid. We argue that that target can only be on the left hand side of the array.
- For right, if the `right == target`, we move low toward high. We don't care if it's `==` or `<`, we just keep moving low forward. We argue that if target is in the right hand side, by the time `low == high`, that indicates right index should be `high - 1`.