---
layout: post
title:  "About uncle Bob's The Last Programming Language keynote"
date:   2016-07-06 10:38:00 +0200
tags:
- programming language
- uncle Bob
- keynote
- functional programming
---

I decided to watch some programming-related videos and I began with uncle Bob's 
keynote [The Last Programming Language][last-language]. In  general I agree with what 
he says, with one exception. Uncle Bob believes that functional programming is important
because it plays well with multicore programming.

[last-language]: https://cleancoders.com/episode/clean-code-episode-0/show?autoplay=true

I don't think that this is the most important value of functional programming. First of 
all, there's a lot of code written out there that is not multicore-aware. That can happen 
for example when single core performance is sufficient. You can laugh as much as you want
about this statement but there are many programs where it is actually very true.

On top of that, there are many non functional programming languages that can support multicore 
programming without necessarily using threads. For example C++ code can use Open MPI, and Python 
code can use the multiprocessing module.

So what's the real added-value of functional programming? From what I have seen so far and 
without being an expert I see that functional code is:

1. Shorter because it uses higher-order functions that can generally be applied to all (uniform) 
collections/data structures
2. Easier to test because functions use immutable code and are side-effect free
3. Easier to read because it avoids branching
4. In general easier to [reason about][reasoning]

[reasoning]: http://www.lispcast.com/reasoning-about-code

Of course we need to be careful about point 3, especially when we talk about parenteses in Lisp code 

![parentheses in Lisp](http://imgs.xkcd.com/comics/lisp_cycles.png)

or code like the [Combinatory Haskell programmer][haskell] (disclaimer: I have never coded in Haskell)

{% highlight haskell %}
s f g x = f x (g x)

k x y   = x

b f g x = f (g x)

c f g x = f x g

y f     = f (y f)

cond p f g x = if p x then f x else g x

fac  = y (b (cond ((==) 0) (k 1)) (b (s (*)) (c b pred)))
{% endhighlight %}

[haskell]: http://www.willamette.edu/~fruehr/haskell/evolution.html

But in general I believe that with good coding conventions functional code can be
readable and easy to understand.