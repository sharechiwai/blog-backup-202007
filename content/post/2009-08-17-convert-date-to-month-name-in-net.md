---
id: 379
title: Convert Date to Month Name in .Net
date: 2009-08-17T08:17:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/17/convert-date-to-month-name-in-net
permalink: /2009/08/convert-date-to-month-name-in-net/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "2563865758144421118"
categories:
  - .Net Tips And Tricks
---
Today, my friend and I tried to find a way to convert date to a month name. E.g. 2008-08-08 to return August.

I tried to use String.Format(TODAY, &#8220;MMM&#8221;) ,String.Format(&#8220;MMM&#8221;,TODAY) &#8230;etc.  
To convert Date to Month Name sound quite simple, unforunately, I have spent quite a long time to find the solution.

Finally, I have find a solution online, which is to use the ToString&#8217;s method.  
E.g. Today.ToString({Format of the date}) to get the date format you want.

**DateTime.Now.ToString(&#8220;MMMM&#8221;)**

Is it quite easy, isn&#8217;t it?

Happy programming = )