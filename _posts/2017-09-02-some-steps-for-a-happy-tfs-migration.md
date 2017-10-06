---
layout: post
title: "Some steps for a happy tfs migration"
date: 2017-09-02 18:14:17
image: '/assets/img/'
description: "This is a live documentation, please help us with your experience in the comments"
main-class: "devops"
color: '#985736'
tags:
- tfs-migration
categories:
- devops
twitter_text: "This is a live documentation, please help us with your experience in the comments"
introduction: "This is a live documentation, please help us with your experience in the comments"
---

After some tfs migrations, you become more confident in various aspects. There are people passing for things that you probably already passed. So, why not help those people?

The main goal of this post is to become a live doc and receive updates and fixes. If you want to help, please feel free to leave comments. I will update the content of the post using your comments. Or even better: send a pull request to the post, I would appreciate that.


## After the migration, let's see what we broke with some basic tests.  
You didn't think that everything would be perfect, did you? Oh, poor padawan, sorry about that.

## Tips and tricks

  * TFS Updates are cumulative. For example, imagine the scenario where you have a TFS 2017 with update 1. The TFS 2017 update 3 will come with all the features of update 2 and, of course, with all the features of update 3.

## Update an offline server
Yes, you didn't read wrong, I really said **offline server**. It's possible to update a TFS on a server without internet connection.

First, you need to download the .ISO version of the update.

Second, your update can't depend on third part software. For example, imagine a scenario where your update will install the search code feature. This feature depends on JRE and the installation won't download this software. Look, you will see an alert like this:
![Warning server without internet]({{ site.baseurl }}/assets/img/steps-tfs-migration/warning-server-without-internet.PNG)

And if you try to install features that depends on third part software, you will see an error like this:
![Error server without internet]({{ site.baseurl }}/assets/img/steps-tfs-migration/error-server-without-internet.png)

It's possible to install the update dependencies separately. So, you can download it using another computer.



# Stay in touch, this post is being written