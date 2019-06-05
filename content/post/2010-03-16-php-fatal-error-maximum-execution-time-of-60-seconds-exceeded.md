---
id: 262
title: 'PHP Fatal error: Maximum execution time of 60 seconds exceeded'
date: 2010-03-16T03:16:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/03/16/php-fatal-error-maximum-execution-time-of-60-seconds-exceeded
permalink: /2010/03/php-fatal-error-maximum-execution-time-of-60-seconds-exceeded/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "34885360885990724"
categories:
  - PHP 新手筆記
---
When I try to run a php function, which contain several sub function that include loop to retrieve data from website and update it to mysql. I have received the following error.  
<span style="font-size:x-small;"><b><span style="color:red;">&#8220;Fatal error: Maximum execution time of 60 seconds exceeded &#8220;</span></b></span>

This error occurs because this function has been execute longer than the maximum execution time. 

**To resolve this issue you can update the following.**  
**1) In php.ini.**  
You can find the following string on the php.ini. And update the maximum execution time according to the time that you need.  
<span style="font-size:x-small;"><b><span style="color:red;">&#8220;max_execution_time = 60     ; Maximum execution time of each script, in seconds&#8221;</span></b></span>

Or  
**2) you can execute the following code before you run that function.**  
<span style="font-size:x-small;"><b>set_time_limit(TimeInSecond); </b></span>//I&#8217;ve used 0 e.g. set\_time\_limit(0); in my case, as I am running it on my computer. 

Hope you find this useful.

Happy programming =)