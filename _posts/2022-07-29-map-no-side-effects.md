---
layout: post
title: "Map results should be free from side-effects"
date:   2022-07-29 19:00:00 +0200
author: Sakis Kasampalis
tags:
- map
- functional programming
- clojure
- side effect
---

When we want to write code that operates on a data structure (collection of items), it is common to initially implement it for a single item, and then make it more general. In functional languages like Clojure I use the following pattern a lot to execute a function on all items of a data structure (aka collection):

{% highlight clojure %}
(defn single-item-function [item]
    (dostuff))

(defn collection-function [collection]
    (map #(single-item-function %) collection))
{% endhighlight %}

So far so good, until I found out that only one of the functions [in my hobby project](https://github.com/faif/sub-matcher) was working fine at the <abbr title="Read-Eval-Print-Loop">REPL</abbr> (Read-Eval-Print-Loop), but not outside of it. Guess what was wrong with that function: It had side-effects!

What's a side-effect?

Generally speaking, a part of code has side-effects when it is nondeterministic. A good example is code that involves <abbr title="Input/Output">I/O</abbr> (Input/Output), like opening a file. You cannot guarantee what the behaviour of that code is, for many reasons. You might execute it once and all goes well; then execute it a second time and it fails badly due to a disk failure, the file was removed or renamed, file permission changes, etc.

So after banging my head for some time, I found out that when calling code with side-effects using `map`, the behaviour is undefined. And that explains why that particular function was working "fine" in the REPL, but not when executing the program normally. 

But wait, how can we fix this? Functional languages have ways of dealing with side-effects, and in Clojure this is done via [`doseq`](https://clojuredocs.org/clojure.core/doseq). So in my case, replacing `map` with `doseq` [in that function](https://github.com/faif/sub-matcher/blob/main/src/sub_matcher/core.clj#L128) was sufficient.