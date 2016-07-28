---
layout: post
title: 'Exploring Swift'
date:   2016-07-27 20:38:00 +0200
author: Sakis Kasampallis
tags:
- swift
- github
- gist
- walkthrough
- functional programming
- objective-C
- java
- android
- ios
---

Before the release of [Swift][swift] I had no interest in doing mobile development. The reason 
was that I'm not a big fan of Objective-C (the only official iOS language before Swift was 
released) and Java (the official Android language). I know that there are workarounds for using
other languages but when it comes to mobile development I prefer using the oficially supported tooling.

[swift]: https://swift.org

Although I am a programming language enthusiast Objective-C never got me excited. And after having worked 
with (or at least explored) languages that are more pragmatic and functional (for example Python, Scala, 
and Clojure) my feelings for Java are similar. Both Objective-C and Java are too verbose and not pragmatic 
enough for doing modern development. 

The rather minimal functional programming support offered by both languages is nothing more than hacks that 
were added after the fact. Programming language features that are not well thought are not a good thing. 
This feels as bad as first implementing a software system and then trying to make it secure: security as an 
afterthought is one of the biggest problems of today's insecure systems. Although I'm still exploring functional
programming I'm pretty sure that most professional functional programmers will agree with me on this.

Fortunately Swift has changed the game. By releasing Swift and also making it free software (or open source if you
prefer this term) Apple surprised me in a positive way and caught my interest. And although I have already bought 
a (so far good) book about [iOS development using Swift][ios9] I feel that I haven't explored core Swift as a 
language enough -- especially its functional features.

[ios9]: https://pragprog.com/book/adios3/ios-9-sdk-development

That's why I've decided to re-read some articles I've been reading since the initial release of Swift. But
this time instead of just reading, I created a playground and fixed/cleaned-up the deprecated features of the
given examples (Swift is evolving very fast, version 3 will be released at the end of 2016). I'll keep my findings
in the following Gist. If you have any suggestions let me know.

<script src="https://gist.github.com/faif/ed9f30e921798299005eb2ebc684451f.js"></script>
