---
layout: post
title:  "Understanding Distributed Systems - Book"
date:   2023-07-22 22:23:37 +0300
categories: books distributed systems
---

I have come across multiple recommendations to the book [Understanding Distributed Systems by Roberto Vitillo](https://understandingdistributed.systems/). 

On a high level, the book goes through a wide range of issues pertaining to distributed systems, ranging from database isolation levels, to a description of the Raft consensus algorithm, to best practices for instrumenting services with logs and metrics. The book in general was easy to read and highly engaging. The book is quite upfront about its breadth-first approach, rather than depth first. It aims to provide engineers with a broad starting point into the world of distributed and large-scale systems.

The book is divided into 5 Parts: Communication, coordination, scalability, resiliency and maintainability.

The first Part (communication) starts by establishing the unreliability of networks on which large-scale systems are built. Then it goes on to explain how reliability can be established on top of unreliable links using IP and TCP as an example. The book continues to go through other essential protocols such as TLS, DNS and HTTP/S (versions 1, 2 and 3), I specifically enjoyed the explanation of the difference between HTTP/S versions and was amused at the concept of using UDP to build a whole new reliable network protocol instead of TCP.

This Part established two important aspects: 
1. The protocols that are most widely used in large-scale, distributed systems, an introduction to type of discourse to expect in this book.
2. The mental model of achieving reliability from unreliable infrastructure, which is carried all throughout the book.

One last note on the first Part, I never really thought of DNS as a distributed, eventually consistent key-value store even though that is exactly what it is. This theme of applying concepts that I would normally attribute to general purpose databases permeates throughout this book. 

The book then moves to the Coordination Part, this Part is the most challenging to read. I have gone through some sections multiple times, it is definitely worth taking your time and not glossing through things you haven't understood. This section in general continues with the theme of building reliability on top of the systems available to us and goes through many things that could go wrong. This section introduced me to many new concepts that I have not been exposed to before. Such as chain replication and the concept of conflict-free replicated data types (CRDTs) which intrigued me so much I had to go and explain this concept to my (very patient) wife. This Part closes on some practical advice regarding supporting asynchronous transactions by describing two common patterns: the outbox pattern and the Saga pattern.

The third Part (scalability), is also a very interesting read. It solidified some concepts in my mind and gave them names (such as _static stability_). It also continues in the theme of applying concepts I usually only consider with databases to the general components of a distributed system. For example, it enlightened me to the fact that putting multiple nodes behind a load balancer applies replication to stateless services and that HTTP caching is an example of _eventual consistency_. This section worked very well in re-framing my thought process more uniformly across the different classes of system components.

I found the last two Parts (resiliency and maintainability) to be closer to my daily experiences as a software development engineer. They explain in detail the concepts and best practices of designing and operating software in this day and age. In general, I found the concepts that these sections go through to be quite close to my day-to-day in designing, implementing and operating highly available software. It is still a valuable read to all engineers as there will be nuggets of valuable information for everyone in there.

One last very positive note about this book is the number of intriguing references in the footnotes which will be my next reading material now that I have finished this book.

In terms of criticism, I haven't found much to complain about as someone who used this book for what it claims to be, a broad introduction into the world of distributed systems. Even though this is not the first book I read on the topic (Designing Data Intensive Applications was my first), it was a valuable resource that I can use as a jumping point into many topics in distributed systems. On that note, one nitpick is that mathematical formulas failed to render correctly on my Kindle, using the EPUB that I got through gumroad. Another criticism is that I felt a major shift in the content during the last section, and it felt closer to software engineering content rather than distributed systems. I considered skipping it, but decided to go through it anyway and I don't regret it as I was able to sail through it quick enough.
