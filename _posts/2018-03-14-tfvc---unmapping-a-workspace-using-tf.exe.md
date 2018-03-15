---
layout: post
title: "TFVC - Unmapping a workspace using tf.exe"
date: 2018-03-14 20:34:23
image: '/assets/img/'
description: Unmapping a workspace via command line
main-class:
color:
tags:
- TFVC
- workspace
categories:
twitter_text: Unmapping a workspace via command line
introduction: Unmapping a workspace via command line
---

Problem: Unmapping a workspace.  

It's possible to do this using visual studio, but I had to do via command line because visual studio wasn't available to me.  

I used a command line utility called tf.exe. This utility can be found on different paths depending on the version of visual studio installed. Here are some versions:

* ***VS 2017*** - C:\Program Files (x86)\Microsoft Visual Studio\2017\<EDITION>\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer
* ***VS 2013 / 2015*** - C:\Program Files (x86)\Microsoft Visual Studio <version>\Common7\IDE

You can see the commands available through this utility by running the tf command or, more specifically, the problem that we solve by running the tf vc help command. See the result of the above commands:  
![Commands output]({{ site.baseurl }}/assets/img/tf1.png)

The first thing I did was check which workspaces were mapped on my machine. I did this using the following command:
> tf vc workspaces /collection:https://wenndersantos.visualstudio.com/defaultcollection/

***/collection:*** is a parameter, here you must put the url of the tfs along with the collection that are checking the mappings. The result of this command is as follows:  
![Commands output]({{ site.baseurl }}/assets/img/tf 2.png)  

The above image shows the return of two workspace mappings on my machine. To delete a mapping, use the following command:
> tf vc workspace /delete /collection:https://wenndersantos.visualstudio.com/defaultcollection/DESKTOP-HTEM3P7

The above command passes the ***/delete*** parameter indicating that the mapping will be deleted. Finally, we add the name of the mapping, which we get using the first command. The result of the command deleting the mapping is this:  
![Commands output]({{ site.baseurl }}/assets/img/tf 3.png)  

After executing the command that deletes the mapping, I executed the command that lists the mappings again to validate if it had actually deleted the mapping, and the result was this:  
![Commands output]({{ site.baseurl }}/assets/img/tf 4.png)  

As the image above shows, we have 1 single mapping. Before running the deleting command, there were two.

Here is the [documentation for the tf tool](https://www.visualstudio.com/en-us/docs/tfvc/use-team-foundation-version-control-commands).

See you on the next post!