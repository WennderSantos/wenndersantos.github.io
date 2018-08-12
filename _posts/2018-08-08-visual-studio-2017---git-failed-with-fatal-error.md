---
layout: post
title: "Visual Studio 2017 - Git failed with fatal error"
date: 2018-08-08 12:25:43
image: '/assets/img/vsgitfail.png'
description: "Git failed with a fatal error. fatal: unable to access 'https://organization.visualstudio.com port:443: Timed out'"
main-class: "editores"
color: '#d662ad'
tags:
- vsts
- vs2017
categories:
twitter_text: "Git failed with a fatal error. fatal: unable to access 'https://organization.visualstudio.com port:443: Timed out'"
introduction: "Git failed with a fatal error. fatal: unable to access 'https://organization.visualstudio.com port:443: Timed out'"
---

After a TFS migration to VSTS, I had a few issues related to Git within Visual Studio 2017.

When I was trying to do anything with Git I was being prompted with the following error:
> Git failed with a fatal error. fatal: unable to access 'https://organization.visualtudio.com port 443: Timed out'

**This problem was just happening with VS 2017**

VS 2017 has a few updates, depending on the updating you are, the fix can be different. Follow some fixes I found and used to made it work in a few different VS versions. You may don't need to apply all the fixes, try to apply one and test if it worked.


## Fix 1: Git proxy configuration

<script src="https://gist.github.com/WennderSantos/22654aa01a88e58317f1f312ae03e5f1.js"></script>


## Fix 2: Visual Studio proxy configuration
Edit the file **devenv.exe.config** in %ProgramFiles(x86)%\Microsoft Visual Studio\2017\Common7\IDE.

<script src="https://gist.github.com/WennderSantos/fe427c37238f063228bab364713e86ec.js"></script>


## Fix 3: Copy VS Git binary files to another folder
This seems to be a bug in the Visual Studio 2017 instalation witch is loading a few Git binaries in a wrong folder/version.
To handle this, you need to copy the right binaries to the right folder like the following:

**From**

> <VS_INSTALL>\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\TeamExplorer\Git\mingw32\bin\

**To**

> <VS_INSTALL>\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\TeamExplorer\Git\mingw32\libexec\git-core\

I had two diferent scenarios for this fix, the first one I copied the bin folder and pasted it inside the git-core folder. In the other scenario, I had to copy all the binaries from the bin folder to the git-core root folder.


## Fix 4: If you are in a Windows 7 or using Git outside Visual Studio
You need to configure Alternate authentication credentials. A few years ago I posted a video showing how to do this. You can see it below.

<iframe width="560" height="315" src="https://www.youtube.com/embed/L5BBx1G6VhU" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>


## Useful links
[Configure Git to use a proxy](https://gist.github.com/evantoli/f8c23a37eb3558ab8765)  
[Proxy Authorization Required](https://msdn.microsoft.com/en-us/library/dn771556.aspx)  
[Copy VS Git binary files to another folder](https://developercommunity.visualstudio.com/content/problem/19752/git-cant-clone-remote-repository.html)  
