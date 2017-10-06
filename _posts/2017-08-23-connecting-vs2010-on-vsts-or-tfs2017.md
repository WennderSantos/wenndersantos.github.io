---
layout: post
title: "Connecting vs2010 on vsts or tfs2017"
date: 2017-08-23 00:57:38
image: '/assets/img/vs2010.png'
description: "Believe me, it's not an uncommon scenario"
main-class: "devops"
color: '#985736'
tags:
- tfs2017
- vsts
- vs2010
categories:
twitter_text: "Believe me, it's not an uncommon scenario"
introduction: "Sometimes we need to deal with scenarios that are not using the last versions of everything. And that's ok, we need to solve our client's problems!"
---

Hello everyone!

Yesterday I had to do some tests to ensure that I could connect Visual Studio 2010 to VSTS or TFS 2017. I am currently working as an ALM consultant, so it's not uncommon to find this kind of scenario at companies.

It wasn't difficult, I just searched on the internet about that and I found some clues that help to resolve the problem. Basically, I just had to install the [Visual Studio SP 1](https://1drv.ms/u/s!AkZjxAmgIji1gZ9R8S6uNpvE3zIPXw) and a [Visual Studio SP 1 KB](https://1drv.ms/u/s!AkZjxAmgIji1gZ9S6CEkzapqoWXDpQ).

After that, everything was working. So, now, the client can connect to their tfs2017 using their Visual Studio 2010. They are planning to migrate to Visual Studio 2017, but until then they can't stop working.

See you on the next post!


## Useful links
[Connecting Visual Studio 2010 Project to TFS on the Cloud](https://blogs.msdn.microsoft.com/africaapps/2013/02/19/connecting-visual-studio-2010-project-to-tfs-on-the-cloud/)

[Visual Studio Client compatibility](https://www.visualstudio.com/en-us/docs/setup-admin/requirements#client-compatibility)
