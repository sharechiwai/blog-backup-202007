---
id: 377
title: This application was precompiled with personalization turned off, but it appears to have been turned on after the precompilation, which is not support
date: 2009-08-19T08:19:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/19/this-application-was-precompiled-with-personalization-turned-off-but-it-appears-to-have-been-turned-on-after-the-precompilation-which-is-not-support
permalink: /2009/08/this-application-was-precompiled-with-personalization-turned-off-but-it-appears-to-have-been-turned-on-after-the-precompilation-which-is-not-support/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "8225461042253733223"
categories:
  - ASP.Net Tips and Tricks
---
I have received a weird error message when I deploy my <span style="font-weight:bold;">ASP.Net</span> application to a server. As you know the application your have developed always works on the development environment (When you are running it via Visual Studio) but some strange error/problems may come up then you run it on LIVE/Production Environment. Therefore I try though I should try it out one of the production server by creating another virtual directory for Live Test purpose..

After copying all the files and folders, I loaded up the website. I received the following error.  
<span style="font-weight:bold;color:rgb(255,0,0);font-size:85%;"></span>

I have no idea why would this happen. I did search through the Web.Config for the word &#8220;profile&#8221; and see if the Web.config get changed after I publish the site. Unfortunately I could not find any string which is related with “profile”.

Finally I just add the line below then the error does not appear again.

<span style="color:rgb(0,153,0);font-size:85%;"><span style="font-weight:bold;"></span></span>

Happy coding