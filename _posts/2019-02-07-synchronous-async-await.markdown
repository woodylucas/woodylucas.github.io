---
title: "“Synchronous” fetching with async await"
layout: post
date: 2019-02-7 22:48
image:
headerImage: false
tag:
- JavaScript
- Async
- Fetch
category: blog
author: woodylucas
description: Markdown summary with different options

---

JavaScript, the language we love, and hate to learn is a synchronous, blocking, single-threaded language. That just means that only one operation can be in progress at a time. This can be such a pain, because what if you want to perform so many task a one time? Many individuals, say hey this language is its opposite asynchronous, but its not. JavaScript can be manipulated to behave in a asynchronously way. Now what does that exactly mean? Well, an asynchronous operation is one that allows the computer to “move on” to other tasks while waiting for asynchronous operations to complete. Asynchronous programming means that time-consuming operations don’t have to bring everything else in our programs to a halt.

Might be a bit confusing, but they’re many example of asynchronicity in our daily lifestyle. Let’s say you’re doing your daily house chores, are you just going to just do everything one by one? I mean you can, but lets say you are on time constraint. We use things such as dishwasher washing our dishes, or a washing machine washing our clothes. While we wait on the completion of those operations, so we’re free to do other chores.

![Alt Text](https://media.giphy.com/media/EvNfyRC5HMVzi/giphy.gif){:height="50%" width="200%"}

Similarly, web development makes use of asynchronous operations. Operations like making a network request or querying a database can be time-consuming, but JavaScript allows us to execute other tasks while awaiting their completion.

But, before dive in deeper into async and await we have to get an understanding on what Promises are.

Promises

A promise is an object that represents the eventful outcome of an asynchronous outcome . A promise has 3 states , that it will rest in: fulfilled, rejected, or pending.

3 States of Promises

- Pending — The initial state — the operation has not completed yet.
- Fulfilled — The operation has completed successfully and the promise now has a resolved value. For example, a request’s promise might resolve with a JSON object as its value.
- Rejected — The operation has failed and the promise has a reason for the failure. This reason is usually an Error of some kind.

When a promise is pending, it can transition to the fulfilled or rejected state. Once a promise is fulfilled or rejected, however, it will never transition to any other state, and its value or failure reason will not change.

Promises are very eager, meaning that a promise will start doing whatever task you give it as soon as the promise constructor is invoked.

Its really highly recommended to understand promises to understand async. You can learn more here.


![Async Await Diagram](/assets/images/async-diagram.png)

Await

As a developer, we will more than likely make a request to APIs a lot. When I first started using fetch, I used it the traditional way(presented below). Async/Await really really goes into solving one of the biggest pains in the language since its beginning: asynchrony. If you do not understand the concept of asynchronous code, I suggest you to read about that first before you keep reading this article.

```javascript


fetch('https://api.com/values/1')
    .then(response => response.json())
    .then(json => console.log(json));

```

What if I said there’s a special type of syntax that you can work with promises, in a more comfortable fashion. This is called async await.

```javaScript

const response = fetch('https://api.com/values/1');
const json = response.json();
console.log(json);


```


But wait, this won’t work. This is normally impossible to do. Now, what if I tell you, you can just insert is a keyword name await.

![Alt Text](https://media.giphy.com/media/vjyl3YVgcLiWA/giphy.gif){:height="50%" width="200%"}

```javascript

const response = await fetch('https://api.com/values/1');
const json = await response.json();
console.log(json);
 

```

1st line of code

Now what exactly is await is doing? Well it is just grabbing a GET request. Instead of heading to the second line, we a(wait) the response to finish. When completed, it passes the response in a response variable.

2nd line of code

Basically the same as first, we are now just getting a JSON response. Remember we are parsing JSON with response.json(), because the promise before returns a json string. But, we then again a(wait) for the response to be complete or failed into a json variable.

3rd line

We can either console.log(json) or return the variable. This just makes are code look a lot cleaner.

RECAP:

A(WAIT) allows us to wait for a PROMISE to resolve to a value.

A(WAIT) will return the value only after the PROMISE is resolved

ASYNC

Oh! wait… there’s more. To make this work, we have to wrap this function in an async.

The word ‘async’ is placed before the function, because it gives it the ability to always return a promise. Even if the function returns a non promise value. Prepending the function definition with the async “ keyword ” basically orders JavaScript to automatically wrap that value in a resolved promise.

Good job! now you’re ready to fetch some data, but before you start I advise learning about Promises.
