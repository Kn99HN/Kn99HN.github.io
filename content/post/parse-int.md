---
title: "Parse Int"
date: 2020-08-01T09:34:43-04:00
draft: false
---

# String to Integer

## Description
Parse a string to an integer not using built in function.

```
"-123"
=> -123
```

## Solution
Though the solution is straightforward, I started it out the difficult way using split. However, it can be easily done with ascii code.

We iterate through the string and we calculate the value using ascii code `val = ord(curr) - 48`. `ord` is a function in python that converts value to ascii code and `48` is the ascii code representing 0. So by taking the difference, we are able to find the current value without using built-in parse function. We then add the val to the `output` by doing 
`output = (output * 10) + ascii`. Eventually, we also check if the `-` ever used, if so, set a flag for the negative value and multiply by -1 at the end.
