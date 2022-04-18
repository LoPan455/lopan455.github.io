---
title: "Marvelous"
date: 2021-08-14T10:23:08-05:00
draft: false
---

# The Origin Story of Marvelous

Marvelous is Spring Boot / Java application that is designed to interact with the Marvel comic book API.  

I started working on this app back in the Fall of 2018, when I first joined Target Corp as an Engineer.  The team I joined maintained a collection of Spring Boot based services, mostly written in Groovy.  At that point in my career I had been working on a tech stack that included PHP, AngularJS, MySQL and Apache. The application we maintained was mostly script-based and my team had begun to migrate portions of the application into an Object Oriented architecture.  To say that I was green in OOP was an understatement.  

So there I was, in a Fortune 30 enterprise organization with a serious amount of ground to cover to understand Java, Groovy and Spring Boot.  No big deal, right?  Wow, was I feeling overwhelmed.  So I got to work using a learning strategy that works pretty well for me: identify a small project or task that seems fun and dig into the learning resources available to get me to my destination. Fortunately, my company provided excellent learning resources, so I jumped in with a project goal in mind: use the Marvel comics public API to fetch and log out some data.  That seemed like a reasonable little "Hello World" task and I was excited to play around with come cool content in order to make it realistic and fun.

Fortunately for me, the Marvel API is well-designed and uses standard, idiomatic (is this the right word to use??) REST principles.  Resource paths are clearly defined, related data is easy to fetch from a given context, and it's overall familiarity with what I already knew about REST APIs made it easy to get started.

What was difficult, however, was everything about Spring Boot.  Wow, was I coming in green here! It took some serious tenacity to stick with learning Spring Boot from scratch, but in the end I was able to get a basic Spring Boot application up and running!  This was a big accomplishment for me at the time. I will often fall back on this project to explore various Spring Boot and JVM language features for a lot of my posts.

# Architecture

As a Spring Boot app, Marvelous exhibits some standard characteristics of a REST API:

* HTTP Controller endpoints exposed to the outside world to handle Create / Read / Update / Delete (CRUD) requests
* A Service layer to process inbound requests, make calls to external data sources.  In its most basic form, the Marvel API itself is the only external data source, but we could easily integrate other data sources
* A Data Access layer to persist data to a database

Another characteristic of Marvelous that posed a challenge was the need to authenticate my API requests.  The Marvel API documentation outlines a specific set of data headers that need to be present on any calls to its API.  This was the most difficult thing to build correctly during my learning process.  

# A Basic GET API call To Fetch Some Data

