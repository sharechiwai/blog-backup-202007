---
id: 435
title: TSQL Get Number of Decimal Place (on a field)
date: 2009-03-04T08:08:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/03/04/tsql-get-number-of-decimal-place-on-a-field
permalink: /2009/03/tsql-get-number-of-decimal-place-on-a-field/
blogger_blog:
  - ourchiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_6870bb21ec74375fd3c4e74cc80d3a54_permalink:
  - "1949656503148393178"
categories:
  - MSSQL Tips and Tricks
---
Today I need to do a query to get all the record which has 3 decimal places on one of the field and process them by using different method.

I am wondering if there any default TSQL function that I can use, so that it can save my time. Unfortunately, I could not find one, so that I decided to write my own function.

Here it is the TSQL code that I used to retrieve the number of decimal place of a field.

<span style="font-size:85%;"><span style="color:rgb(0,153,0);">&#8211;Example input value</span><br /><span style="color:rgb(0,153,0);">DECLARE @DecimalValue FLOAT</span><br /><span style="color:rgb(0,153,0);">SET @DecimalValue = 12.34567</span><br /><span style="color:rgb(0,153,0);">&#8211;Declare a variable to store the result</span><br /><span style="color:rgb(0,153,0);">DECLARE @NoOfDecimalPlace INT</span></p> 

<p>
  <span style="color:rgb(0,153,0);">SET @NoOfDecimalPlace = CHARINDEX(&#8216;.&#8217;, REVERSE(CAST(@DecimalValue AS VARCHAR(30)))) -1</span>
</p>

<p>
  <span style="color:rgb(0,153,0);">&#8211;Return Number of decimal Place</span><br /><span style="color:rgb(0,153,0);">SELECT @NoOfDecimalPlace</span><br /></span><br />Here it is my User Define Function for get number of decimal place of a number field.
</p>

<p>
  You can execute it by using the following SQL code
</p>

<p>
  <span style="color:rgb(0,153,0);font-size:85%;">SELECT dbo. Get_NoOfDecimalPlace(0.123)</p> 
  
  <p>
    CREATE FUNCTION [dbo].[Get_NoOfDecimalPlace]<br />(
  </p>
  
  <p>
    @ValueToProcess FLOAT=0<br />)<br />RETURNS INT<br />AS<br />BEGIN<br /> &#8212; Declare the return variable here
  </p>
  
  <p>
    DECLARE @NoOfDecimalPlace INT<br /> SET @NoOfDecimalPlace = CHARINDEX(&#8216;.&#8217;, REVERSE(CAST(@ValueToProcess AS VARCHAR(30)))) -1
  </p>
  
  <p>
    RETURN @NoOfDecimalPlace<br />END</span>
  </p>
  
  <p>
    Hope you found it useful.
  </p>