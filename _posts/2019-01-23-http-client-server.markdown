---
title: "A Client Server Model: HTTP"
layout: post
date: 2019-01-23 22:44
image:
headerImage: false
tag:
- HTTP
- Internet
- Web Development
star: true
category: blog
author: woodylucas
description: How the internet was built.
---
Since conception, the purpose of the web was to reframe information, and the way we work together. In 1989, a computer scientist named Tim Berner -Lee, wrote a memo. The memo suggested a global hypertext system. Was built out of frustration, due to that fact that you had to be wired to a new machine to have access to certain data-formats.

A Client Server Model is a distributed communication framework in which a client send a request to a server, and a server provides a response queries. A client can be a web browser with just HTML, or just a mobile application FETCHING information over the web. The most used protocol in the world and, is used to build a client server model, is HTTP.

When we mention HTTP, we need to mention how WEB works.

HyperText Transfer Protocol .

![Alt Text](https://media.giphy.com/media/4sJFhJN94QR7W/giphy.gif){:height="50%" width="200%"}


Devised by Tim Berner-Lee, HTTP is an application layer protocol that allows, web-based applications to communicate and exchange data. HTTP is the messenger of the web.

Web pages are mostly designed using the hypertext markup language, or HTML, but with HTTP it can also be used to deliver contents, such as images, videos, audios, documents etc.

URL (Uniform Resource Locator)
This is probably the most familiar concept users use on the web, but did you know it one of the most important attributes of the web? Computers can connect to web servers simply to request a files at a simple address.

A basic url is separated into 5 parts.

![URL Diagram](/assets/images/url-diagram.png)

Protocol : The protocol declares how your web browser should communicate with a web server when sending or fetching a web page or document. Which is the http.

Domain : A domain name is a unique reference that identifies a web site on the internet

Path : The path typically refers to a file or directory on the web server, e.g. /directory/file.php.

Parameters: Parameters are snippets of information found in the query string of a URL.

Fragment: A hash sign (#) in a URL is referred to as a fragment. Historically, URL fragments have been used to automatically set the browser’s scroll position to a predefined location in the web page.

HTTP Request Methods

The heart of REST.

![HTTP Diagram](/assets/images/http-diagram.png)

When a computer is simply fetching data, it usually sends an HTTP message called a GET request, and when it’s sending form data or uploading a file it uses other formats of messages called PUT or POST requests. You can see the HTTP messages your web browser is sending in many browsers through the built-in developer tools.

Today, HTTP is used by many applications other than web browsers to send messages to servers. People creating applications choose HTTP on purpose because it’s well understood by many developers and partly because HTTP is typically unfiltered by network firewalls designed to allow web traffic, meaning that HTTP messages can get through without a problem on most home and business networks.
