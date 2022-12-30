---
layout: post
title: "Dirty clouds"
date:   2022-12-29 20:30:00 +0200
author: Sakis Kasampalis
tags:
- AWS
- cloud
- IAC
- terraform
---

![Cloud and Linux](/assets/cloud.png)

Ideally, all resources of a cloud environment should be handled by Infrastructure As Code (<abbr title="Infrastructure As Code">IAC</abbr>). At work, we are using Terraform to do this. But as usual, the ideal situation is never what happens in practice. So, it is not uncommon for people to change things directly on the cloud environment: in our case, using the AWS console.

If the resource that is "dirty" is already tracked in source code, it is usually fine. When trying to deploy, Terraform will report the difference, so that gives us the chance to update the code and fix the dirty change issue. Note: Always inspect carefully the recommended Terraform action(s) before deploying, because a dirty change has often unwanted effects. A concrete example is when a user makes a relational database change directly on the cloud environment, like increasing the size of a connection pool. As soon as you try to deploy using IAC, Terraform suggests to drop and create the database again. That's the last thing that we want for a database, because all existing data will be lost! The proper action in this case is to modify the code so that the connection pool size number matches the one of the cloud environment.

Another problem with dirty clouds appears when people create a new resource that was not previously tracked in IAC. That's similar to making code changes without using any form of source control. It's not possible to know who did what, and there's no change history whatsoever. What do we do in that case? Although it's not possible to recover the history of changes that happened so far, we can still import the resource to IAC and track all future changes. Importing is a two step process. First, we need to define the resource in infrastructure code, so that it matches (exactly) the cloud resource. The next step is to import the resource using a command like `terraform import`. Hashicorp has a nice hands-on 
[tutorial](https://developer.hashicorp.com/terraform/tutorials/state/state-import) about importing cloud resources.
