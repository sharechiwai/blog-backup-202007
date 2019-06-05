---
id: 370
title: How to convert float into 2 decimal places
date: 2009-08-27T08:27:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/27/how-to-convert-float-into-2-decimal-places
permalink: /2009/08/how-to-convert-float-into-2-decimal-places/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "2396311119597777540"
categories:
  - MSSQL Tips and Tricks
---
Today, I have to check the data which is generate by my program against the record that the company had, to see if my program works properly, so that we can upgrade the process.

One of the tricky part of that process is to covert one of the SQL field into 2 decimal places. I did some research online, finally I found a solution for that.

It looks quite simple:

What you need to do is to convert the **float/money** into a **decimal/numeric** by using the **CAST** Keyword on SQL Server.

Here it is the example.

**decimal[(p[, s])] and numeric[(p[, s])]</p> 

<span style="font-weight:normal;"><span style="color:rgb(51,153,102);">DECLARE @NumToConvert FLOAT</p> 

<p>
  SET @NumToConvert = 123.56789
</p>

<p>
  SELECT CAST(@NumToConvert AS DECIMAL(10,3))</span></span></strong>
</p>

<p>
  <span style="color:rgb(51,153,102);">&#8211;CAST([*Number to convert] AS DECIMAL([*Precision], [*Scale]))</span>
</p>

<p>
  <strong>*Number to Convert</strong> = The number which you want to convert from
</p>

<p>
  <strong>*Precision</strong> = is the number of character(Number) you have from the number that you want to convert from
</p>

<p>
  <strong>*Scale</strong> = is the number of decimal place you want to have.
</p>

<p>
  Normal I would set the <strong>*Precision</strong> to 20, to make sure the size of the number is less than the precision we set. 20 should be big enough. Otherwise you may receive an error <strong>&#8220;Arithmetic overflow error converting float to data type numeric.&#8221;</strong>
</p>

<p>
  For more information about Decimal or Numeric please visit the following URL
</p>

<p>
  <a title="Data Tyoe decimal and numeric SQL 2000" href="http://msdn.microsoft.com/en-us/library/aa258832%28SQL.80%29.aspx" target="_blank">http://msdn.microsoft.com/en-us/library/aa258832(SQL.80).aspx</a>
</p>

<p>
  Please correct me if my concept is wrong.
</p>