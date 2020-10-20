---
title: "Meeting Rooms"
date: 2020-10-13T13:58:53-04:00
draft: false
---

# Meeting Rooms II
## Description

Given an array of meeting time intervals consisting of start and end times [[s1,e1],[s2,e2],...] (si < ei), find the minimum number of conference rooms required.

Example 1:
```
Input: [[0, 30],[5, 10],[15, 20]]
Output: 2
```

Example 2:
```
Input: [[7,10],[2,4]]
Output: 1
```
## Solution
I was confused about the questions at first. But it's pretty similar to merge intervals. We identify that we still need to sort all the meeting based on the start time of the meeting. However, we notice that the room must be free to be reused and if not, we reallocated the room.

So we use a min-heap for this. Our key will be the ending time. Our conditions are as follows:
1. If the current time is `<=` the next meeting, then we remove it from our heap and add the new meeting in.
2. If not, we can just keep adding meetings.

Eventually, our heap will be all the room we need
