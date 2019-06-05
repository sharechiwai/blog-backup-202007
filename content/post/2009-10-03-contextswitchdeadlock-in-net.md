---
id: 353
title: '&#8220;ContextSwitchDeadlock&#8221; in .Net'
date: 2009-10-03T10:03:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/10/03/contextswitchdeadlock-in-net
permalink: /2009/10/contextswitchdeadlock-in-net/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4448478814395962736"
categories:
  - .Net Tips And Tricks
---
<div style="margin:0;">
  A friend of mine asked me how to solve the &#8220;<span style="font-weight:bold;">ContextSwitchDeadLock</span>&#8221; exception problem, every time he has his <span style="font-weight:bold;">C# application</span> run, it throws the below exception and causes the program crash.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Here is the solution:
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  In your <span style="font-weight:bold;">Visual Studio</span>, click on &#8220;<span style="font-weight:bold;">Debug</span>&#8221; from the main menu
</div>

<div style="margin:0;">
  Select &#8220;<span style="font-weight:bold;">Exceptions&#8230;</span>&#8220;
</div>

<div style="margin:0;">
  then Click on the &#8220;+&#8221; sign to extend the &#8220;<span style="font-weight:bold;">Managed Debugging Assistants</span>&#8220;
</div>

<div style="margin:0;">
  Uncheck the check box on &#8220;<span style="font-weight:bold;">ContextSwitchDeadLock</span>&#8221; so that it will not throw the exception about the Dead Lock anymore.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Hope you find it useful.
</div>