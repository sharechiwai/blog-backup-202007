---
id: 359
title: Unable to install or run the application. The application requires that assembly xxx version xx.x.x.x be installed in the Global Assembly Cache (GAC)
date: 2009-09-21T09:21:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/21/unable-to-install-or-run-the-application-the-application-requires-that-assembly-xxx-version-xx-x-x-x-be-installed-in-the-global-assembly-cache-gac
permalink: /2009/09/unable-to-install-or-run-the-application-the-application-requires-that-assembly-xxx-version-xx-x-x-x-be-installed-in-the-global-assembly-cache-gac/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "5298304594875077212"
categories:
  - .Net Tips And Tricks
---
My friend have some problem on installing a Windows application  
After he published to the **central server** for another user use.

The error he received is  
**_&#8220;Unable to install or run the application. The application requires that assembly xxx version xx.x.x.x be installed in the Global Assembly Cache (GAC) first._**

**_Please contact your system administrator.&#8221;  
_**  
Solution  
In order to solve that problem. What you need to do is to check if the assembly/reference is included on the project. if not, please try to include it.

1) Double click on the application name on Visual Studio.  
2) Click on **&#8220;Publish**&#8221; tab.  
3) Click on the **&#8220;Application Files&#8221;** button

![](http://social.msdn.microsoft.com/Forums/getfile/98701)  
4) Check which filename/reference/assembly that the error message said it is missing.  
E.G.  
.![](http://social.msdn.microsoft.com/Forums/getfile/98700)  
5) On **&#8220;Publish Status&#8221;** select **&#8220;Include&#8221;**  
6) After you have included all the required reference. Click &#8220;OK&#8221;  
7) Finally, you can republish the application and check if it works.

Good Luck