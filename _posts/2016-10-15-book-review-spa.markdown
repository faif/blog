---
layout: post
title: 'Book review: Single Page Web Applications'
date:   2016-10-15 14:58:00 +0200
author: Sakis Kasampalis
tags:
- javascript
- single page application
- mongodb
- manning
---


![Book cover](/assets/spa.jpg)

I decided to read [this book][spa] because I wanted to learn about the architecture
and implementation of a Single Page Application (SPA). And it turned out to be
a good choice.

[spa]: https://www.manning.com/books/single-page-web-applications

What I particularly liked about the book is that it begins from scratch and
shows how to implement a SPA without relying on heavy frameworks. Whenever a
library is used, it is done with a purpose (clearly explained by the authors).

That helps to understand the internals of a SPA without any framework getting
in your way. Once you understand how a SPA works, using a framework is not a
problem. But you have the option of using it or going your own way.

Since I'm not very experienced in JavaScript, I found Chapter 2 (Reintroducing
JavaScript) very useful. It covers topics like the two code passes of the
JavaScript engine, how JavaScript is different than common OOP languages by
being a prototyping language, the module pattern, and self-executing anonymous
functions.

There are more interesting stuff covered in this SPA book: Static code analysis
using jslint, unit testing, and persistence using MongoDB are some of them.

The only cons are that it (1) is a big book, (2) doesn't demonstrate
how to plug many features of modern SPAs (for example smooth scrolling,
infinite scrolling, and jumbotron) in the proposed architecture.

Recommended to anyone interested in implementing SPAs and/or improving their
JavaScript skills :)
