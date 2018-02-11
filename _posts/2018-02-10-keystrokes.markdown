---
layout: post
title: 'Type less, do more...'
date:   2018-02-10 17:00:00 +0200
author: Sakis Kasampalis
tags:
- typing
- autojump
- bash
- productivity
---

If you are dealing a lot with the terminal you probably use the `cd` command very often. `cd here`, `cd there`, `cd ..`, etc. What if I told you that you can avoid typing the `cd` command completely? That can save you a lot of keystrokes which is good because it:
* Makes you more productive
* Helps you avoid <abbr title="Repetitive Strain Injury">RSI</abbr> problems, such as the infamous <abbr title="Carpal Tunnel Syndrome">CTS</abbr>

The first tool that I want to show you is [autojump](https://github.com/wting/autojump). Once installed, autojump (abbreviated by the command `j`) maintains its own database to help you navigate to a directory without the need to remember:
* Where the directory actually is
* The full name of the directory (partial names will do)

Here's an example of using autojump to quickly open my website's repo directory.

![autojump example](/assets/autojump.gif) 

If you give to autojump a name pattern that is not yet familiar with, it will simply ignore it and stay to the current directory. So what can you do to save some keystrokes until the database of autojump is good enough, or when visiting unexplored territories? `autocd` to the rescue!

Modern bash versions (>= 4.0) support a builtin option called `autocd`. That allows you to navigate through directories without the need to use the `cd` command. Combine it with a few shell wildcards and it will save a lot of routine typing. To enable the `autocd` option all you need is `shopt -s autocd`. Put the command in a profile/initialization file to make the setting persistent. Follows an example of how you can use `autocd` to quickly (and using minimum keys) open a (yet unknown to `autojump`) directory.

![autocd example](/assets/autocd.gif)