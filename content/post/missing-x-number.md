---
title: "Missing X Number"
date: 2020-08-13T21:32:45-04:00
draft: false
---

# Missing Numbers
## Description
We have an array from 1 to N with one number missing, we would like to find the missing number.


# Solution
We know there is one number missing, hence the max value must be the length of the array plus the x missing numbers. Therefore, we can easily calculate the sum with Gaussan formula of n*(n+1)/2. We then just need to subtract from all the numbers in the array to find the missing number. 

This, however, will only work if there is one number missing. If there are 2 numbers missing, we calculate the multiplication of all values up to maximum value. We then use quadratic formula to calculate the 2 missing numbers.

Not sure if there are solutions for x numbers missing, but Albert gave an advice of remembering that the value is also the index in the array.