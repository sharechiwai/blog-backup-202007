---
id: 325
title: TSQL Divide problem, Decimal not shows. “/”
date: 2010-02-05T02:05:00+08:00
author: ShareChiWai
layout: post
guid: 'http://sharechiwai.wordpress.com/2010/02/05/tsql-divide-problem-decimal-not-shows-%e2%80%9c%e2%80%9d'
permalink: '/2010/02/tsql-divide-problem-decimal-not-shows-%e2%80%9c%e2%80%9d/'
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "1912234795388941590"
categories:
  - MSSQL Tips and Tricks
---
Today I try to create a round up function on TSQL, which is use to override the normal Round function that provided by MSSQL server.  
When I try to do 1/10, it returns 0 rather than 0.1  
It is so strange  
E.G.  
<span style="color:#009900;font-style:italic;">DECLARE @i AS FLOAT</span>  
<span style="color:#009900;font-style:italic;">SET @i=1</span>

<span style="color:#009900;font-style:italic;">SELECT @i/10</span>

I tried it several time, and asked my friend how to do it as well.  
Unfortunately we have no idea as well.

Finally, I just remember i had similar problem before, I solved it by putting a decimal number onto the value and it just work fine again.

E.g.  
<span style="color:#009900;font-style:italic;">DECLARE @i AS FLOAT</span>  
<span style="color:#009900;font-style:italic;">SET @i=1.0</span>

<span style="color:#009900;font-style:italic;">SELECT @i/10</span>

Then I went to MSDN to read up about it, it said:

Result Type  
<span style="color:#3333ff;font-style:italic;"><</p> 

<p>
  <span style="color:#3333ff;font-style:italic;">If an integer dividend is divided by an integer divisor, the result is an integer that has any fractional part of the result truncated.>></span>
</p>

<p>
  For more information please visit the URL below.<br /><a href="http://msdn.microsoft.com/en-us/library/ms175009.aspx11">http://msdn.microsoft.com/en-us/library/ms175009.aspx11</a>
</p>

<p>
  Hope you find it useful.</span>
</p>