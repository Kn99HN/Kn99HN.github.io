---
layout: post 
title: Sequential Consistency - A Mental Model
---

Continuing with my theme of mental model, today, we will visit **sequential consistency**. I was first introduced to this term in my Operating Systems course, during the concurrency unit. I dind't quite understand what it means. I registered the word to my brain and called it a day.

I then revisited the term during my Distributed Systems course where we learned about sequential consistency's big and powerful brother, linearizability. That's when I really needed to understand what sequential consistency means.

I will present my mental model of sequential consistency below. Assume we have 2 processes, foo and bar. Each process executes a set of commands and writes to a shared memory/register. However, foo doesn't know what bar does and vice versa. The only person who knows is me, the omniscient observer. 

For instance:

```
foo: ------(1)-----------(2)

bar: ---(3)-------------------(4)

1: int n = i;
2: i = i + 1;

3: int n = i;
4: i = i + 1;

i is a global value that both process can writes to

We denote (NUMBER) as event number NUMBER
```
In the example above, we observe that (3) comes before (1) and (2) comes before (4). But recall each process has its own view of what it's doing and no what the others are doing. Therefore, foo doesn't know the actual ordering of bar's code. 

This is where sequential consistency comes in. Sequential consistency allows re-ordering of events across multiple processes but NOT within a single process.

For example, here are the correct orderings of sequential consistency:

```
(1)----(2)-----(3)----(4)

(1)-----(3)-----(2)----(4)

(3)----(1)------(2)----(4)

(3)----(1)------(4)------(2)

...
```

You might think that we can order (2) before (1). NO! That's not what sequential consistency allows. So these are incorrect:

```
(1)-----(2)-----(4)------(3)

(2)-----(3)------(4)------(1)

...
```

These are incorrect because we are re-ordering events within a SINGLE process, which is never allowed under the assumption of sequential consistency. However, we are allowed to re-order events across MULTIPLE process as long as order of events in the same process is preserved.