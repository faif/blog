---
layout: post
title: 'Wheels says no...'
date:   2018-11-02 22:00:00 +0200
author: Sakis Kasampalis
tags:
- wheels
- python
- pep-440
---

![Computer says no](/assets/computer-says-no.jpeg) 

After porting one of our libraries at work in Python 3, I wanted to publish it as a package. The tool that we are using to distribute packages is 
[wheels](https://pythonwheels.com). 

Unfortunately, wheels was refusing to create the package. It was reporting an error similar to the following: `wheel.cli.WheelError: "Bad wheel 
filename mypackage-latest-cp36-cp36m-linux_x86_64.whl"`.

After searching online without any luck, I found a GitHub issue mentioning [PEP 440](https://www.python.org/dev/peps/pep-0440/). Well, it turns out
that the "latest" part of the package name is not very PEP 440 compliant... So wheels was right to complain. And all I had to do was modify the 
name to make it compliant. The PEP document has many [examples](https://www.python.org/dev/peps/pep-0440/#examples-of-compliant-version-schemes) of 
compliant schemes, so if you are facing a similar error pick any scheme that fits you.