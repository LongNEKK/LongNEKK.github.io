---
layout: essay
type: essay
title: "Connections and Capillaries"
# All dates must be YYYY-MM-DD format!
date: 2026-04-30
published: true
labels:
  - Engineering - Design Patterns - Project Management 
---

<img width="200px" class="rounded float-start pe-4" src="../img/bootstrap.png">

# Structure, Anatomy, and Policy: The Things Written in Blood

To dissect the workflows and processes of an organization may seem like a stale and cold endeavor, and yet when presented with an opportunity for investigation, these kinds of observations are rarely comparable to the clinical measurements of a cadaver. Instead, these probing movements lead to jerky, sporadic outbursts and movements that lead one to believe that the entity under the scope may be alive indeed. Oftentimes, the stereotypically drab corporate nature presented in media might lead one to underestimate the liveliness with which software projects are made. For every line, there was a request, a consideration, a debate, and even a story. When unexpected changes occur, the lifeblood of the project spurts back out - leading the most and least experienced alike to reach for the gauze. For every policy and convention, there was a scar that healed. In much the same way, there are capillaries known as design patterns. They carry the waste and the nutrients all throughout the system, and maintain the health of the project body. They are often small, simple in scope, and yet they carry the weight of the project in their multitudes. 

## The Veins That Run; The Veins That Bleed

Throughout a project, there may seemingly be endless lines of code - functions and critical data to maintain throughout an indefinite period of time. The oil of the machine must run; the body's blood must flow. It becomes critical to analyze how one can influence the overall health of the system without disturbing its performance too drastically. In this process, we look at the capillaries - the tiny structures and habits that build up the whole system through their reproducibility and utilitarian nature. They often carry waste - such is the job of memory clean up operations. In other cases, the capillaries must bring the critical nutrients to their locations - the database writing to a page and vice versa. Importantly, the patterns are essentially the same and can be found potentially anywhere. As we poke and prod at these patterns, we find complications - technical debt that prevent a system from achieving its full potential. In other cases, we observe and marvel at the perfect blood vessel - a function called an endless amount of times while never feeling in its intended purpose.

## Our Own Lifeblood

As we approach the end of the semester, it becomes important to recognize and analyze the movement and health of our very own system. The interactions between people will inevitably create a real, practically living thing amidst their presence. Performing my very own examination, I have noticed several design patterns that improve the functionality of our system. Rather than having dozens of pages for separate courses on our rate-your-course app, we fill out a template page UI element from a database based on the relevant fields. In addition, our course catalog contains many cards for separate courses. Similar to our course detail page, these card elements are simply filled in with information from our database. Separately, we also maintain a global CSS style guide that all elements abide by, and build off of locally. Finally, the page elements are kept as modules separate from the actual page so that the debugging is easier and clearer when determining if an issue is a React issue, session-data related, or a Nextjs issue. Observing our very own design patterns has often been against our will - we've had to take our scopes with us to evaluate precisely where the bleeding was happening. As we continue our project, we have only one thing on our minds. Where'd I put the bandages? 

