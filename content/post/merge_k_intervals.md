---
title: "Merge K sorted lists"
date: 2020-09-06T17:44:49-04:00
draft: False
---

# Merge K Sorted Lists

## Description
You are given an array of k linked-lists lists, each linked-list is sorted in ascending order.

Merge all the linked-lists into one sorted linked-list and return it.

```
Input: lists = [[1,4,5],[1,3,4],[2,6]]
Output: [1,1,2,3,4,4,5,6]
Explanation: The linked-lists are:
[
  1->4->5,
  1->3->4,
  2->6
]
merging them into one sorted list:
1->1->2->3->4->4->5->6
```

## Solution
This is Shoup's problem but I was asked by Albert this. I really
appreciate when Albert asked me interview questions. Even though
he is not a seasoned interviewer like Nick, he still has lots of
insights in the questions about the problem's strategy.

So the most brute force solution I came up with is to insert
all the elements in the lists of lists inside a heap. The heap
will take care of sorting all the values for us. In the end,
we will have a sorted lists. The run time is O(n*k log(n*k))
with n being the average number of each sorted list and k
is the total number of sorted lists.

However, to optimize on this with a heap,we can insert a list
instead of a value, reducing the number of elements in the heap.
We also need to change the comparator of the heap to accept
an object instead of an integer. Moreover, each pop we do with
the heap, we then retrieve the first element of the current list
and re-insert the `curr.next` into the heap so that the heapify
characteristic of the data structure is maintained. Runtime is
O(k*log(n*k))

Lastly, Albert points me to the solution without a heap. For
this solution, we fall back to the problem where we merge 2 sorted
linked list. We also rely on merge sort for this solution. Therefore,
we first divide up all the lists until we have `len(lists) <= 2`.
At this point, we can either merge them as we do with 2 sorted linked
list or return it if there's only 1. In the end, the runtime
is the same but our space complexity is a lot better!

