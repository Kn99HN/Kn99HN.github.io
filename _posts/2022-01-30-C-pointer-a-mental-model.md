---
layout: post
title: Demistifying C pointer - A Mental Model
---

C is fun to learn! The C pointer is a concept in the language that deals with memory allocation. Dynamic allocation on the heap is impossible without pointers.

As I led a section for my Operating Systems course, I realized that students often don't have a good mental model of C pointers. Rightfully so, lots of CS students were not taught how to think abstractly about the problem or how to build a good mental model when working with new concepts. So in this blog post, I'm going to go over a mental model for thinking about the C pointer. But first, what is a mental model?

[Wiki](https://en.wikipedia.org/wiki/Mental_model) definition of a **Mental model**: A mental model is an explanation of someone's thought process about how something works in the real world.

My definition of a **Mental model**: A way to think about the concepts without concerning too much with the nitty details.

"C pointer is just a memory address. THAT'S IT. Repeat it 25 times and you'll get it" - my OS professor.

The statement is true. A C pointer is an address in memory. In another word, it's a variable whose value is a memory address. That's a mouthful. So let's break it down by building up our mental model. I will show you mine.

Let's look at an example:

```
int a = 1;
int* b = &a;
int** c= &b;
```

"*" *denotes the pointer type in C. "&" means "get me the memory address of the variable to the right of &".* "***" can be confusing. Sometimes, you would see it used as an operator, called dereference operator. Here's my mental model for the example above:

```
Code                Stack (on x86-64)
int a = 1;    ->     a [   1   ] 0x108
int* b = &a;  ->     b [ 0x108 ] 0x116
int** c = &b; ->     c [ 0x116 ] 0x124
```

As you see, each variable declaration is a box with its name, value, and memory address drawn on a stack. The first declaration is specifying that `a` is stored on the stack with value `1`. Then `b` will have the address of `a`, which is `0x108`. Subsequently, `c` will have the address of `b`, which is `0x116`.

As we dereference these pointers, we just need to follow the box that it points to. I think pointers get a lot of bad reps. But it's not a mystery at all. Rather, it's a very intuitive concept!

