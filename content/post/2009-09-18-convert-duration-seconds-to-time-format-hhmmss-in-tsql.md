---
id: 362
title: Convert Duration seconds to Time format HH:MM:SS in TSQL
date: 2009-09-18T09:18:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/18/convert-duration-seconds-to-time-format-hhmmss-in-tsql
permalink: /2009/09/convert-duration-seconds-to-time-format-hhmmss-in-tsql/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "3038151078836158231"
categories:
  - MSSQL Tips and Tricks
---
<span class="Apple-style-span" style="font-family:'Times New Roman';"></p> 

<div style="width:auto;font:normal normal normal 100%/normal Georgia, serif;text-align:left;border-color:initial;border-style:initial;border-width:0;margin:0;padding:3px;">
  In my previous post, I have created a method on crystal report function to convert duration in seconds to Time format. I think it would be useful to have another one for TSQL as well.</p> 
  
  <p>
    Here it is my User Define function to convert duration (Seconds) to Time format.<span style="font-weight:bold;">Hours:Minutes:Seconds</span>.
  </p>
  
  <p>
    Hope you find it useful.
  </p>
  
  <p>
    <span style="color:rgb(0,153,0);font-size:85%;">CREATE FUNCTION [dbo].[ConvertDurationToTime]<br />(<br />&#8212; Add the parameters for the function here<br />@Duration INT = 0<br />)<br />RETURNS VARCHAR(12)<br />AS<br />BEGIN<br />&#8212; Declare the return variable here<br />DECLARE @ConvertedTime VARCHAR(10)</p> 
    
    <p>
      &#8212; Add the T-SQL statements to compute the return value here<br />DECLARE @HH VARCHAR(5)<br />DECLARE @MM VARCHAR(3)<br />DECLARE @SS VARCHAR(3)
    </p>
    
    <p>
      IF LEN((@Duration / 3600))<span style="color:rgb(0,0,0);"><br />Happy Coding</span></span></div> 
      
      <p>
        </span><br /><span style="color:rgb(0,153,0);font-size:85%;"><span style="font-size:100%;"><span style="color:rgb(0,0,0);"><br /></span></span></span>
      </p>