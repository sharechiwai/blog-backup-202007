---
id: 373
title: Display source code/HTML code on Blog/WebSite
date: 2009-08-23T08:23:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/23/display-source-codehtml-code-on-blogwebsite
permalink: /2009/08/display-source-codehtml-code-on-blogwebsite/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "3571891796395730059"
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
I tried to paste a sample code of a JavaScript function on blogspots (on Compose mode), unfortunately, it have get rendered. When I publish the post I cannot see any of my Javascript.

After trying it several time, finally I have figured out how to show HTML/Javascript source code on a blog post.  
Here it is the solution:  
1) Replace all the &#8220;<span style="font-weight:bold;"><</span>&#8221; with &#8220;<&#8221; and &#8220;<span style="font-weight:bold;">></span>&#8221; with &#8220;>&#8221; (with out the &#8220;speech mark&#8221; surrounded it)  
2) create a PRE tag on the Edit HTML code just before where you want to place the source code. if you do not use the 

<pre>tag the code that you placed on Edit HTML mode will lost all the format and it will look mess.<br />3) Once you done that you can place your source code in Edit HTML Mode.<br />4) make sure you closed the </pre>

tag.  
5) Click on the &#8220;Compose mode&#8221; or the Preview button to check if it can show the code as what you expected.

Good luck