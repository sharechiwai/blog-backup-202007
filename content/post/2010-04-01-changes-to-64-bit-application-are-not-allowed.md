---
id: 243
title: Changes to 64-bit application are not allowed.
date: 2010-04-01T04:01:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/04/01/changes-to-64-bit-application-are-not-allowed
permalink: /2010/04/changes-to-64-bit-application-are-not-allowed/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "6535339380118370737"
categories:
  - .Net Tips And Tricks
---
64-bits development environment seems to make life more difficult, when I try to edit my code on debug mode or after hitting the break point, a popup message come up and tell me that I cannot not do what I used to do when I was using 32 bits development environment.

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/changesto64bitsapparenotallowed.png" style="margin-left:1em;margin-right:1em;"><img border="0" src="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/changesto64bitsapparenotallowed.png?w=625" data-recalc-dims="1" /></a>
</div>

I find it easier, to have the ability to edit the code on the debug mode , so that you can test out the code by using different programming logic/variable [while stepping through the break point] &#8230;etc.

Fortunately, I have find a way to work around this issue.

<div style="margin:0;">
  Here it is my solutions.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  1) On Visual Studio Open &#8220;<b>My Project</b>&#8221; from the &#8220;<b>Solution Explorer</b>&#8220;
</div>

<div style="margin:0;">
  2) Click on the &#8220;<b>Compile</b>&#8221; Tab
</div>

<div style="margin:0;">
  3) Then Click on &#8220;<b>Advanced Compile Options&#8230;</b>&#8220;
</div>

<div style="margin:0;">
  Select &#8220;<b>Advanced Compiler Setting</b>s&#8221; -> Update Target CPU property to &#8220;<b>x86</b>&#8221; instead of &#8220;<b>Any CPU</b>&#8220;
</div>

<div style="margin:0;">
  <img height="454" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/f3fef2d42b2a46e9bbe720261a8403c2" width="553" />
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  I am able to edit my code in the debug mode, after I set the break point.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Happy coding. 
</div>