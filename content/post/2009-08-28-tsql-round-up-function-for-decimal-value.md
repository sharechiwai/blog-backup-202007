---
id: 369
title: TSQL Round Up function for Decimal Value
date: 2009-08-28T08:28:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/28/tsql-round-up-function-for-decimal-value
permalink: /2009/08/tsql-round-up-function-for-decimal-value/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "1477869725918365363"
categories:
  - MSSQL Tips and Tricks
---
These few weeks I was working on a project which needs to deal with decimal place.  
I was struggle with it for very long time =(.  
One of the processes on the program is to round up the value from 4 decimal (4dp) places to 3 decimal places (3dp)

I had done some research; I do not think there is a Default function from MSSQL that I can use to force it to round up a value. Although it does has a function for you to round down a value.

Anyway I have created my User define function which allow me to specific the number of decimal place that I want to round up to and the value that I would like to round.

<span style="color:rgb(0,153,0);font-style:italic;font-size:85%;">CREATE FUNCTION [dbo].[RoundUpToGivenDecimalPlace]<br />(<br /> &#8212; Add the parameters for the function here<br /> @SourceValue </span><span style="color:rgb(0,153,0);font-style:italic;font-size:85%;">MONEY</span><span style="color:rgb(0,153,0);font-style:italic;font-size:85%;">= 0,<br /> @DecimalPlace INT = 1<br />)<br />RETURNS FLOAT<br />AS<br />BEGIN</p> 

<p>
  DECLARE @RoundResult MONEY
</p>

<p>
  DECLARE @ValueToAdd </span><span style="color:rgb(0,153,0);font-style:italic;font-size:85%;">MONEY</span><br /><span style="color:rgb(0,153,0);font-style:italic;font-size:85%;"> SET @ValueToAdd = @DecimalPlace +1</p> 
  
  <p>
    SET @ValueToAdd = 4.0/POWER(10,@ValueToAdd)
  </p>
  
  <p>
    SET @RoundResult= ROUND(@SourceValue+@ValueToAdd, @DecimalPlace)
  </p>
  
  <p>
    &#8212; Return the result of the function<br /> RETURN @RoundResult<br />End</span>
  </p>
  
  <p>
    Hope your find it useful.
  </p>