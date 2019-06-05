---
id: 372
title: Crystal Report Convert Time Format From Seconds to HH:MM:SS
date: 2009-08-25T08:25:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/25/crystal-report-convert-time-format-from-seconds-to-hhmmss
permalink: /2009/08/crystal-report-convert-time-format-from-seconds-to-hhmmss/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "6635337131718669549"
categories:
  - Crystal Report Tips and Tricks
---
Some of the Crystal report that I need to generate involve conversion between Seconds to <span style="font-weight:bold;">Hours:minutes:seconds</span>.  
I spend quite a long time to search on internet and work out how to do it and experienced some bugs on one of the <span style="font-weight:bold;">Crystal Report</span> <span style="font-weight:bold;">formula </span>that I build before had a bug.  
I am not sure why it only works on some computer, but not the other.  
E.g. it always display 2 decimal places at the end i.e. 1.00. (Although I use Mod to retrieve the reminder of the number, which mean it should not have any decimal place at all)  
Anyway, here it is the formula/code that I use to convert Seconds to HH:MM:SS  
Hope you find it useful:

<span style="color:rgb(51,102,255);font-size:85%;">numberVar dur;</span><span style="font-size:85%;"><br /></span><span style="color:rgb(51,102,255);font-size:85%;">dur := </span><span style="font-style:italic;color:rgb(51,102,255);font-size:85%;">{Field/Value/Seconds you want to convert}</span><span style="color:rgb(51,102,255);font-size:85%;">;</span><span style="font-size:85%;"><br /></span><span style="color:rgb(51,102,255);font-size:85%;">numberVar hrs;</span><span style="font-size:85%;"><br /></span><span style="color:rgb(51,102,255);font-size:85%;">numberVar min;</span><span style="font-size:85%;"><br /></span><span style="color:rgb(51,102,255);font-size:85%;">numberVar sec;</span><span style="font-size:85%;"><br /></span><span style="color:rgb(51,102,255);font-size:85%;">stringVar hhmmss;</span><span style="font-size:85%;"></p> 

<p>
  </span><span style="color:rgb(51,102,255);font-size:85%;">hrs := Truncate(Truncate(dur/60)/60);</span><span style="font-size:85%;"><br /></span><span style="color:rgb(51,102,255);font-size:85%;">min := Remainder(Truncate(dur/60),60);</span><span style="font-size:85%;"><br /></span><span style="color:rgb(51,102,255);font-size:85%;">sec := Remainder(dur,60);</span><span style="font-size:85%;"></p> 
  
  <p>
    </span><span style="color:rgb(51,102,255);font-size:85%;">hhmmss := totext(hrs,&#8221;00&#8243;) + &#8220;:&#8221; + totext(min,&#8221;00&#8243;) + &#8220;:&#8221; + totext(sec,&#8221;00&#8243;);</span><span style="font-size:85%;"></p> 
    
    <p>
      </span><span style="color:rgb(51,102,255);font-size:85%;">hhmmss</span>
    </p>