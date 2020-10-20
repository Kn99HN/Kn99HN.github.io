---
title: "Minimum Cost for Tickets"
date: 2020-10-19T22:15:05-04:00
draft: false
---

# Minimum Cost For Tickets
## Description
In a country popular for train travel, you have planned some train travelling one year in advance.  The days of the year that you will travel is given as an array days.  Each day is an integer from 1 to 365.

Train tickets are sold in 3 different ways:

    a 1-day pass is sold for costs[0] dollars;
    a 7-day pass is sold for costs[1] dollars;
    a 30-day pass is sold for costs[2] dollars.

The passes allow that many days of consecutive travel.  For example, if we get a 7-day pass on day 2, then we can travel for 7 days: day 2, 3, 4, 5, 6, 7, and 8.

Return the minimum number of dollars you need to travel every day in the given list of days.

```
Input: days = [1,2,3,4,5,6,7,8,9,10,30,31], costs = [2,7,15]
Output: 17
Explanation: 
For example, here is one way to buy passes that lets you travel your travel plan:
On day 1, you bought a 30-day pass for costs[2] = $15 which covered days 1, 2, ..., 30.
On day 31, you bought a 1-day pass for costs[0] = $2 which covered day 31.
In total you spent $17 and covered all the days of your travel.
```

## Solution
Our base case:

1. Our index or traversal go out of bound => return 0.
2. The current day is `<=` the covered days, i.e the current days have been covered by our pass. If so, just continue.
3. If the current day is in the cache/map, return its value.

Our step:

We need to make 3 traversals:
- Buy 1 day pass.
- Buy 7 day pass, covering next 7 days from current day.
- Buy 30 day pass, covering next 30 days from current day.

We will then return the minimum value of the threes.


