---
title: "“Synchronous” fetching with async await"
layout: post
date: 2019-02-7 22:48
image:
headerImage: false
tag:
- markdown
- components
- extra
category: blog
author: woodylucas
description: Markdown summary with different options

---

JavaScript, the language we love , and hate to learn is a synchronous, blocking, single-threaded language. That just means that only one operation can be in progress at a time. This can be such a pain, because what if you want to perform so many task a one time? Many individuals, say hey this language is its opposite asynchronous, but its not. JavaScript can be manipulated to behave in a asynchronously way. Now what does that exactly mean? Well, an asynchronous operation is one that allows the computer to “move on” to other tasks while waiting for asynchronous operations to complete. Asynchronous programming means that time-consuming operations don’t have to bring everything else in our programs to a halt.

Might be a bit confusing, but they’re many example of asynchronicity in our daily lifestyle. Let’s say you’re doing your daily house chores, are you just going to just do everything one by one? I mean you can, but lets say you are on time constraint. We use things such as dishwasher washing our dishes, or a washing machine washing our clothes. While we wait on the completion of those operations, so we’re free to do other chores.

As a developer, we will more than likely make a request to APIs a lot. When I first started using fetch, I used it the traditional way(presented below). Async/Await really really goes into solving one of the biggest pains in the language since its beginning: asynchrony. If you do not understand the concept of asynchronous code, I suggest you to read about that first before you keep reading this article.
