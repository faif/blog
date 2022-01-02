---
layout: post
title: "When in trouble, ssh -vvvvvv :)"
date:   2022-01-02 10:00:00 +0200
author: Sakis Kasampalis
tags:
- ssh
- key
- passwordless
- dsa
- rsa
---

![xkcd tar](/assets/tar.png) 

I was configuring a new server and what's the first thing that we want to setup when doing that? Passwordless ssh of course.

So after following all required steps, I tried to connect. And it failed (still required a password)… So what do we do in that case?
* Ensure that the key was copied to the remote machine (e.g. by `ssh-copy-id`). Yep, looks good.
* Check all related dir and file permissions of both local and remote computers (`.ssh` and its contents). All good.

So what the heck is wrong? Let's run ssh in (max) verbosity using `ssh -vvv` (3 v is the max, adding more v is just for fun):

{% highlight bash %}
…
debug1: Skipping ssh-dss key .ssh/id_dsa - not in PubkeyAcceptedKeyTypes
…
{% endhighlight %}

Gotcha! The server is properly configured to reject DSA keys, since [DSA is deprecated][dsasec] because it is considered insecure.

So what went wrong here? Well, I have both DSA and RSA keys in my `.ssh` dir, and I copied the wrong key using `ssh-copy-id`. I should probably get rid of the DSA key completely at some point :)

[dsasec]: https://security.stackexchange.com/questions/112802/why-openssh-deprecated-dsa-keys