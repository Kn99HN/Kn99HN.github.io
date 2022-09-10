---
layout: post 
title: Sequential Consistency - A Mental Model
---

Continuing with my theme of the mental model, we will visit **sequential consistency**. I didn't understand the concept when I was first introduced during my Operating Systems course. I called it a day by registering the word to my brain.

I revisited the term during my Distributed Systems course where we learned about sequential consistency's big and powerful brother, linearizability.

I will present my mental model of sequential consistency below. Assume we have 2 processes, `foo` and `bar`. Each process executes a set of commands and writes to a shared memory/register. However, `foo` doesn't know what `bar` does and vice versa. The only person who knows is me, the omniscient observer. For instance:

```
foo: ------(1)-----------(2)
bar: ---(3)-------------------(4)

--- EVENT NUMBER ---
(1): int n = i;
(2): i = i + 1;
(3): int n = i;
(4): i = i + 1;
```

`i` is a global value that both processes can writes.

In the example above, we observe that (3) comes before (1), and (2) comes before (4). However, each process has its own view of what it's doing. On the other hand, each process does not know what the others are doing. Therefore, `foo` doesn't know the actual ordering of `bar`` ’s events.

This is where sequential consistency comes in. Sequential consistency allows re-ordering of events across multiple processes but NOT within a single process.

Here is a sequential consistent ordering of the example above:

```
(1)----(2)-----(3)----(4)
(1)-----(3)-----(2)----(4)
(3)----(1)------(2)----(4)
(3)----(1)------(4)------(2)
```

We cannot order `(2)` before `(1)`. That's not what sequential consistency allows. From `foo`‘s perspective, it knows that `(2)`  comes after `(1)`. This is an incorrect ordering:

```
(1)-----(2)-----(4)------(3)
(2)-----(3)------(4)------(1)
```

It is incorrect because we are not allowed to re-order events within a SINGLE process under the assumption of sequential consistency. However, we are allowed to re-order events across MULTIPLE processes as long as the order of events in the same process is preserved.