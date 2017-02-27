---
layout: post
title: "Some tips to make your VSTS build runs faster"
date: 2017-02-19 22:12:51
description: "\"Time is money!\" Reduce your build's execution time"
main-class: 'devops'
color: '#985736'
tags:
- vsts
categories:
twitter_text: "\"Time is money!\" Reduce your VSTS build's execution time"
introduction: "\"Time is money!\" Reduce your VSTS build's execution time"
---

Most of these tips I found on internet ([references](#references)) and a few of them I discovered doind some tests.

## Incremental build
In a continuous integration build, I think it's ok to execute incremental builds.  
Probably, from all the tips, this will be the one that will cause the biggest impact on your build execution time.  
On VSTS, you can enable incremental build by unchecking the **clean** configuration like the image below:  
![VSTS clean configuration]({{ site.baseurl }}/assets/img/tips-build-faster/01.png)

If you got interested to know more about incremental build, take a look at these links:
  * [Incremental Builds](https://msdn.microsoft.com/en-us/library/ee264087.aspx)
  * [How to: Build Incrementally](https://msdn.microsoft.com/en-us/library/ms171483.aspx)
  * [Configure Team Foundation Build for an Incremental Build](https://msdn.microsoft.com/en-us/library/aa833876(v=vs.100).aspx)


## Disable windows defender real-time protection
When your build is running, open the task manager. You will see a process called **Antimalware Service Executable** using almost 100%
 of the computer process.


<a name="references"></a>
## References  
<a href="http://ardalis.com/speed-up-visual-studio-build-times">http://ardalis.com/speed-up-visual-studio-build-times</a>  
<a href="https://www.codeproject.com/Tips/1042975/Tips-to-Improve-Visual-Studio-Build-Performance">https://www.codeproject.com/Tips/1042975/Tips-to-Improve-Visual-Studio-Build-Performance</a>
