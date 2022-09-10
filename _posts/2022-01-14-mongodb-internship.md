---
layout: post
title: MongoDB - Internship done right
---

<p class="message">
This is my first blog post. So exciting!
</p>
<br/>

As a junior, I haphazardly found an internship before graduation. This was what I wanted during college. Seeing so many posts on LinkedIn, I was ambitious to gain one internship offer.

I hit a low point during October. I tried balancing classes and interviews. While others found internships during September, I was struggling until late October.

Fortunately, I received an internship offer from MongoDB around Thanksgiving of 2020. This might have been my happiest moment during that year.

## Preface

As I looked at the list of incoming interns, I saw a few familiar schools: CMU, Cornell, UC Berkeley, UPenn, et al. I was the only intern from NYU. Nervous might be an understatement. I was scared shitless. Those were all household names for CS. The students must be incredibly competitive and technically inept. Looking forward to June 2021, I did not know what to expect. I had never interned at an established company before.

## Community

All the interns were incredibly nice, helpful, and down-to-earth people. Due to ongoing cases of COVID in NYC, the recruiting team couldn't organize lots of in-person events. Despite the difficulties, they would occasionally organize picnics in Central Park or game nights. Additionally, we had roundtables with every engineering team in the company: Driver, Server, Cloud, Developer Productivity, and even coffee chats with the executives on the C-suite! It was super inspiring to talk to the CTO, Mark Potter.

As an intern, we were given 2 options: hybrid[^1] and remote. I chose hybrid along with 40 interns. The recruiting team grouped all the interns on the same floor. This helped form bonds between our intern class quickly due to proximity. We always hung out in a big group settings. So much so that full-time engineer were intimidated to go down to the 37th floor for lunch because we would group all the tables into one.

Outside of organized events, our intern class also went out a lot. Emphasize A LOT. I didn't have much of a traditional college experience at NYU. But I got all of that in one summer[^2].

Aside from the interns, my team was very sociable and supportive. I had weekly check-ins with my mentor and bi-weekly check-ins with my team lead. Both contributed to my growth tremendously.

## Technology

It's time to talk about technical projects. After all, it's a software engineer internship. I will go over some aspects of my work but won't go into too many details due to my signed NDA.

I was an intern on Cloud Insights & Telemetry team, which owns the Data Explorer page on Atlas, metrics and performance graphs for customers, and other metrics-related products at MongoDB.

In the beginning, I worked on warm-up tickets (a.k.a quick wins). They were small and required less codebase knowledge. I picked up tickets on both the front-end and back-end to ramp myself up. These were fun since I could finish them in a day.

After one warming up week, I started working with my co-intern, Chrispine. Our project focused on upgrading the Data Explorer search bar. We wanted to replace the search bar component developed by the [Compass team](https://github.com/mongodb-js/compass).

I picked up most backend tickets since I preferred working on them. The new search bar comes with more options for the users to query. One of my tickets ended up being a lot bigger than I expected. However, it was interesting because I applied an object-oriented programming concept to the ticket, which I did not expect before.

To my surprised, I'd write more unit, integration, and E2E tests than the actual code itself. At first, I think they were inconveniences that prevented me from shipping. As more bugs arose throughout my software development process, I learned to appreciate them.

After finishing my portion of the project, I tackled the team’s backlog. I fixed small bug tickets across the stack, and added small features throughout Atlas.

Here's the new search bar on the front end that I helped develop.

![https://kn99hn.github.io/assets/images/Atlas-Search-Bar.png?raw=true](https://kn99hn.github.io/assets/images/Atlas-Search-Bar.png?raw=true)

### Lessons

Here are what I learn after my internship:

- Debugging in a large codebase can be painful. Debuggers are your friend. Frontend - [Firefox debugger](https://developer.mozilla.org/en-US/docs/Tools/Debugger). Backend - [IntelliJ Debugger](https://www.jetbrains.com/help/idea/debugging-code.html).
- Force yourself to switch debugging styles. I rely too much on print statements at the beginning of my internship. I force myself to use a debugger.
- Inspect is your friend on the front end.
- IntelliJ's Annotate feature is helpful to understand the codebase's history.
- Sometimes, certain things are done for a reason. It's better to ask than changing it.
- Switch your code reviewers. It's good to have different perspectives on your code.
- Sandbox your time. Try all you can. However, if you haven't figured it out, ask someone. There's no reason to be blocked by something that others might know.
- Test, test, and test: unit, integration, E2E, and QA.
- Look up in the codebase first! Someone might have created the tools for the use cases.
- Socialize!

## Conclusion

It was such an incredible opportunity for me to meet others and learn software development from one of the best tech companies. Not only did I progress as a software engineer but also as a person. I owed my gratitude to the Cloud Intel team and my fellow interns, who made it such a memorable event in my life. Here's a photo of us during our last get-together

![https://kn99hn.github.io/assets/images/MongoDB-interns.JPG?raw=true](https://kn99hn.github.io/assets/images/MongoDB-interns.JPG?raw=true)

[^1]: It slowly evolved into full in-person internship since they allowed interns to come in 5 days a week.

[^2]: I also guided people to lots of restaurants, which will be a post of its own.