---
id: 336
title: Display TimeStamp / DateTime as yyyyMMddHHMMSS string in .Net use as Filename.
date: 2010-01-23T01:23:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/01/23/display-timestamp-datetime-as-yyyymmddhhmmss-string-in-net-use-as-filename
permalink: /2010/01/display-timestamp-datetime-as-yyyymmddhhmmss-string-in-net-use-as-filename/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4278939376750986497"
categories:
  - .Net Tips And Tricks
---
It would be a good idea to put a timestamp onto a filename, if your application/process that export a file or generate a file for user to download.  
E.g.  
Filename_YearMonthDaysHourMinuteSecond.txt  
yyyyMMddhhmmss  
Example_20100123123456.txt

It is quite simple to use .Net to generate a TimeStamp as a string.  
**Here it is the solution:**

**VB**  
<span style="background-color:white;color:#38761d;">String.Format(&#8220;{0:yyyyMMddhhmmss}&#8221;, Today.Now)</span>

**C#** [which is very similar as VB]  
<span style="color:#38761d;">string.Format(&#8220;{0:yyyyMMddhhmmss}&#8221;, DateTime.Now)</span>

<span style="color:#38761d;"><span style="color:black;">Hope you find it useful =) </span><br /> </span>