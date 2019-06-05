---
id: 344
title: Display Date Format in GridView ASP.Net
date: 2009-12-21T12:21:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/12/21/display-date-format-in-gridview-asp-net
permalink: /2009/12/display-date-format-in-gridview-asp-net/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "6665314138525388634"
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
---
<div style="margin:0;">
  Sometime you may want to display a Date on a Grid view on your ASP.Net application. When you retrieve the data from database, which is in Date Format.
</div>

<div style="margin:0;">
  It often displays date and time together and may not display it into the correct format you want. E.g. 21-12-2009 00:00:00 rather than 21-12-2009&#8230;etc</p>
</div>

<div style="margin:0;">
  The get around this problem:
</div>

<div style="margin:0;">
  You just need to add one attribute on your code on the .aspx file
</div>

<div style="margin:0;">
  <span style="color:red;">DataFormatString</span>=&#8221;<span style="color:blue;">{0:dd-MM-yyyy}</span>&#8221; /></p> 
  
  <p>
    Hope you find it useful.</div>