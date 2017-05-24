---
layout: post
title: 'SFTP: How to fix the "Host key verification failed" problem'
date:   2017-05-24 19:50:00 +0200
author: Sakis Kasampalis
tags:
- nodejs
- sftp
- problem
- host key verification failed
---

I'm busy with a Node.js project at work. The project requires SFTP support and for that we decided to use the [ftps] module. Although I was able
to connect to the SFTP server using `lftp` and FileZilla without any problems, the Node.js project was failing. By checking the logs of the project I noticed that the cause was the infamous "Host key verification failed" problem.

Since SFTP uses SSH, it requires an initial key exchange between the client (in this case, my computer) and the server. Apparently the ftps Node 
module cannot deal with this key exchange. One solution is to force this procedure using the classic `ssh` command. Even if the SFTP server is
configured not to allow remote shell connections (usually it connects to `nologin` or `false`), it will do the job.

So, if you are using SFTP in your software project and you are dealing with host key verification failures, try connecting to the server using an 
SSH client first.

[ftps]: https://www.npmjs.com/package/ftps
