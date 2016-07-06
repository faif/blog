---
layout: post
title:  "And the second conference of the year was... NextBuild"
date:   2016-07-03 20:10:00 +0200
categories: nextbuild conference 2016
tags:
- conference
- nextbuild
- '2016'
- eindhoven
---
It's sad that there are no good programming conferences in the South of the Netherlands and especially around the Eindhoven
area which is considered very innovative and has a strong university. Fortunately, [NextBuild][nextbuild] is an exception.

[nextbuild]: http://nextbuild.nl

2016 was the second year of the NextBuild conference. I missed the first one so I can't comment about it, but I can say a few
things about the 2016 version. First of all it's important to stress that this is a free (gratis) one day conference, which is
not the usual case when it comes to conferences ([Dutch Clojure Days][dcd] was another good exception). And even though NextBuild is free, 
we were offered free coffee, juice, cookies, sandwiches, and beers. Not bad...

[dcd]: {{site.url}}/2016/05/21/and-first-conference-of-year-was-dutch.html

But let's move one to the interesting parts: the actual content. The agenda was full of [parallel talks][talks] so I had to make my 
choices. But the first keynote was common. Pini Reznik talked about *Cloud Native Applications and Post-DevOps*. Pini obviously believes in
software automation since he said that:

> Autonomous software is as inevitable as autonomous cars and planes

[talks]: http://nextbuild.nl/agenda/

Pini's ideas involve self-healing and auto-scaling cloud software. Not only I agree with those ideas, but as an operating system fan I would
like to see them be supported not only in cloud software, but in all software, including operating systems.

The next keynote I joined was *Coding the Next Build* by Niek Palm. This keynote focused on using Docker for everything, especially on stuff that
are usually not version-controlled, like the build system's configuration. I have not even played with Docker yet, but what I see is that people are
very passionate about it. This is usually a bad sign (think of XML), since geeks are not subjective about a technology when they get very
excited with it. In general the war between package managers, virtual machines, and containers is a mess. Although I see the point behind Docker, it is 
generally accepted that it needs more mature tooling and that it is not the solution for all problems.

Next, Joost den Boer talked about *Gettings started with cool IoT stuff*. What I liked about this keynote was that Joost did not talk about Arduino or
Raspberry Pi, which by now everybody knows about (or at least has heard of). Instead he showed alternative (and actually cheaper) platforms that can be
used for IoT development. Particularly, [RedBear Duo][redbear] and [PINE64][pine] look very interesting. But for now, I'll stick to my (nowadays old
school!) [mbed LPC1768][mbed] microcontroller :)

[redbear]: https://github.com/redbear/Duo
[pine]: http://pine64.com
[mbed]: https://developer.mbed.org/platforms/mbed-LPC1768/

Matthijs Groen spoke about *SpeedLazer: Lunch break game development*. Developing a functional game during lunch breaks is remarkable. But apparently it
is possible using modern frameworks like [Phaser][phaser]. Brian Hogan wrote a nice article in June's pragpub about *Making a 2D Game in Phaser*. It's
[available for free][hogan], so download it and have some fun!

[phaser]: http://phaser.io
[hogan]: http://theprosegarden.com/wp-content/uploads/2013/09/Hogan.pdf

In the next talk Yegor Bugayenko mentioned the *Seven Deadly Sins of a Software Project*. If there's one thing that should be kept from this talk is:

> The history of commits is as valuable as the source code

Indeed the commit history is very important and that's why we should not create a monster out of it. So this advice goes hand-by-hand with [How to Write
a Git Commit Message][git].

[git]: http://chris.beams.io/posts/git-commit/

Next, I joined the keynote *Service Discovery in a Microservice Architecture using Consul* by Jos Dirksen. I haven't heard of [Consul][consul] before so it was 
good to see some demos about how it can be used in a microservice based architecture. No further comments...

[consul]: https://www.consul.io

Marcin Czenko's talk was about *Fast prototyping with React and Firebase*. [Firebase][firebase] is yet another tool that I didn't know about. I am aware of 
[React][react] but I have never used it. The nice thing about Firebase is that it supports many languages (including Swift) and many platforms.

[firebase]: https://firebase.google.com
[react]: https://facebook.github.io/react/

The last presentation of the day was *Modern JavaScript: Object-oriented thinking in a functional world* by Egbert Teeselink. Egbert talked about 
[immutable-js][immutable] which is a soft way of introducing support for immutable, persistent data structures in JavaScript. It's nice to see that
JavaScript is trying to follow the examples of the functional programming languages that I like, namely Clojure and Scala. I'm still busy with how 
to write proper modern mutable JavaScript code, but when I'm passed this stage immutable-js is something to consider. Although I have the impression that ClojureSript 
is a better approach.

[immutable]: https://github.com/facebook/immutable-js

See you next year NextBuild ;)