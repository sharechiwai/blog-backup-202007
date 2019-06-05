---
id: 367
title: Open/Launch a file/Application in .Net Window Application
date: 2009-09-13T09:13:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/13/openlaunch-a-fileapplication-in-net-window-application
permalink: /2009/09/openlaunch-a-fileapplication-in-net-window-application/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "8028785175068740515"
categories:
  - .Net Tips And Tricks
---
Today my friend need to launch my Windows application via his windows application.  
Our application are both on a server.

To archieve that what we need to do is to use **Process.Start()** method

**Diagnostics.Process.Start(**full file path and name**)**  
E.g.  
VB  
<span style="color:rgb(0,153,0);font-size:85%;"><strong>Diagnostics.Process.Start(&#8220;C:Program FilesInternet Explorer.exe&#8221;)</strong></span>

C#  
<span style="color:rgb(0,153,0);font-size:85%;"><strong>Diagnostics.Process.Start(@&#8221;C:Program FilesInternet Explorer.exe&#8221;);</strong></span>

After you done that you should be able to launch/open the file by clicking on a button&#8230;etc

Good luck