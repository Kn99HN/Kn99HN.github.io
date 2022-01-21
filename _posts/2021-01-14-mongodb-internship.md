---
layout: post
title: MongoDB - Internship done right
---

<p class="message">
This is my first blog post. So exciting!
</p>
<br/>

As a junior, I haphzardly found an internship before graduation. To be honest, this is what I have been building up to my time at college. Seeing so many others post on LinkedIn, I was ambitious to gain 1 internship myself.

I hit a low point during October. I tried balancing course work and interviewing. While others often found internship during September, I was struggling until mid November.

Eventually, I accepted an internship offer from MongoDB around Thanksgiving of 2020. This might have been the happiest moment during that year.

## Preface

As I looked at list of incoming interns, I saw the few familiar schools: CMU, Cornell, UC Berkeley, UPenn, etc.. I was the only intern from NYU. Nervous might be an understaement. I was scared shitless. Those were all household names for CS. The students must be incredibly competitive and technically inept.

Looking forward to June 2021, I did not know what to expect. I have never interned at an established company before. In my head, I imagine 60 SWEs intern in the room talking about the most in-depth CS topics. Boy, was I wrong.

## Community

To my surprise, all the interns are incredibly nice, helpful and down to earth people. Due to ongoing cases of COVID in NYC, the recruiting team couldn't organize lots of in-person event. Despite the difficulties, the recruiting team would occasionally organize picnice in Central Park or game night. Additionally, we have roundtables with every engineering team in the company: Driver, Server, Cloud, Developer Productivity and even coffee chats with the executives on the C-suite!

As intern, we are given 2 options: hybrid[^1] and remote. I chose hybrid and about 30-40 interns chose this option. This option was great because the office was fully remote back then. So they have all the intern on the same floor. This helps form bonds between our intern class because we would work together, chat together and eat lunch together. We were always hanging out in big group. So much so that fulltimers were intimidated to go down to our floor for lunch because we would group all the tables into one.

Outisde of organized events, our intern class also goes out a lot. Emphasize on A LOT. I personally don't have much of a traditional college experience at NYU. But I definitely get all of that in 1 summer[^2].

Aside from the intern class, my team was also very great and supportive. I'd have weekly check-ins with my mentor and bi-weekly checkins with my team lead. Both contributes to my growth tremendously over the summer, technically and personally. What MongoDB lacks, they made up for it with an incredible work environment.

## Technology

It's time to talk about technical projects. After all, it's a SWE intern. I was there to learn about software development. I will go over some aspects of my work but won't go into too much details due to my signed NDA.

I was an intern on Cloud InTel, which owns Data Explorer page on Atlas, metrics and performance graphs for customers, and other metrics-related products at MongoDB.

At the beginning, my mentor had me work on a few warm-up tickets. These are refered to as quick win tickets. They were small and require less knowledge about the codebase. I picked up tickets on both the front-end and back-end to getting myself familiar with the Cloud codebase. These were fun since I can finish in a day or 2. 

After 1 week of setting up, I started working on my co-intern, Chrispine, on upgrading Data Explorer search bar. We were looking into replacing the search bar with the one used by the [Compass team](https://github.com/mongodb-js/compass). Though the task seems trivial at first, it requires complex changes throughout the codebase. 

I picked up on most backend tickets since I prefer working on them. The new search bar comes with more options for user to look at their data. These requests come from the front-end. So my job is to correctly parse and issue the commands. Along the way, I ran into refactor issues. So one of my tickets end up being a lot bigger than expected. But it was interesting because I was applying object-oriented programming concept into the ticket, which I did not expect before. 

Another surprising aspect I did not realize is the amount of testings required for each ticket. Sometimes, I'd write more tests, unit, integration and/or E2E tests than the actual code itself. At first, I think they were hassle that prevents me from coding more. However, slowly, as more bugs arise throughout my software development process, I learned to appreciate them.

After finishing my portion of the project, I tackled on the backlog of the team: fixing up small bug ticket across the stack, adding small features here and there. These tickets were mundane at times but I think it allows me look at what the customer reports and ticketifying it into digestible description so that whoever work on it can understand the context without having lots of knowledge in the codebase.

### Bugs

Story time!!!

So what is the point of internship if you don't cause trouble along the way, right?

I was very fortunate to have a supportive team, interns and environment to learn. Along the way, I definitely made a lot of mistakes. Quite a few serious ones, actually.

### Strike one
The 1st bug came in my backend improvement. When users update a document, a request is sent back to the server to be done in the database itself. However, what will happen if the user didn't change anything and only enter the update state? Well, an empty request is sent back to the server and data will be wiped for that JSON object. Fortunately, another member on my team caught and patched the bug.

### Strike two
The 2nd bug came when I was working on another piece of software in our stack. Let's call it X. X accepts/allows certain commands. For my ticket, we would like X to accepts a command Y. However, for a serveless ticket that my co-worker worked on, X shouldn't be allowed to accept command Y. So, what happens? No one saw this coming so my ticket was merged in first. However, this triggers a failures in an E2E test, which is required to pass to be able to be merged into the codebase. So my change ends up blocking my teammate. I quickly resolve this issue but it blocks him for a few days.

### Strike three
The 3rd bug came on the last day of my internship. 1 hour before my laptop is shut down by the systems. There has been changes in the code base regarding tests. However, I didn't know this and wrote test in the old manner, which passes at the time and is merged into the main branch. However, as the new tests requirements came in, my code breaks the setup, preventing all other PRs to be merged. Lucky for me, it was easily fixed by reverting the commits and happended on a Friday afternoon, when everyone already clocked out. The bug actually helps my Director of Engineer improve the setup! [^3]

Here's the new search bar on the front-end. It looks a lot cooler, init?

![](https://kn99hn.github.io/assets/images/Atlas-Search-Bar.png?raw=true)

## Conclusion
That's a wrap. It was such an incredible opportunity for me to meet others and learn software development from one of the best tech companies. Not only did I progress as a SWE but also a person. I owe my gratitude to Cloud Intel team and my fellow interns, who made it such a memorable event in my life. Here's a photo of us during our last get-together

![](https://kn99hn.github.io/assets/images/MongoDB-interns.JPG?raw=true)

[^1]: It slowly evolves into full in-person since they allow intern to come in 5 days a week.

[^2]: I also guide people to lots of restaurants, which will be a post of its own.

[^3]: Or atleast that's what he said to make me feel better.


