---
id: 351
title: 'Runtime Error: Arithmetic overflow error converting expression to data type INT'
date: 2009-10-07T10:07:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/10/07/runtime-error-arithmetic-overflow-error-converting-expression-to-data-type-int
permalink: /2009/10/runtime-error-arithmetic-overflow-error-converting-expression-to-data-type-int/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "8228996788724276167"
categories:
  - MSSQL Tips and Tricks
---
<div style="margin:0;">
  I try to run one of the stored procedure I created long time ago by taking out the whole stored procedure and run it in SQL Query Analysis. (In this case I do not need to save the Stored procedure and run it on different query analysis to check the output &#8230;etc)
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  I just re-declare the parameter.
</div>

<div style="margin:0;">
  <span class="Apple-style-span" style="font-size:small;"><b><span style="color:#38761d;">DECLARE @i INT</span></b></span>
</div>

<div style="margin:0;">
  <span class="Apple-style-span" style="font-size:small;"><b><span style="color:#38761d;">SET @i =20090202000000</span></b></span>
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  When I run the stored procedure it returns the following error in few minutes after. (my query is going to retrieve 7 millions row and insert it into another table)
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  <span style="font-weight:bold;">&#8220;Runtime Error: Arithmetic overflow error converting expression to data type int&#8221;</span>
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  I have check/test it several time, it still return the same error.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  <span style="font-weight:bold;">Will it something caused by the Parameter?</span>
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Finally I check the data type of the parameter of my stored procedure; the data type is BigInt instead of Int.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  I just realise I made a silly mistake.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  But I can learn from mistake. If i receive the same error message &#8220;Runtime Error: Arithmetic overflow error converting expression to data type int&#8221;
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  The first thing I am going to do is to check the data type/value of my variable.
</div>

<div style="margin:0;">
  And make sure the size of the parameter is large enough for the value&#8230;
</div>

<div style="margin:0;">
  HaHa.
</div>