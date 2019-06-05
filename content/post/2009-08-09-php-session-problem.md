---
id: 386
title: PHP Session Problem
date: 2009-08-09T23:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/09/php-session-problem
permalink: /2009/08/php-session-problem/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "268071425024980380"
categories:
  - PHP 新手筆記
---
When I try to use the Session variable in PHP $_Session[&#8220;VariableName&#8221;], it does not work&#8230;.  
The session never get registered.

How to check?  
You can use the following code to see if the Session is null or not.  
<span class="Apple-style-span" style="color:#FF0000;"><?php</span>  
    <span style="color:rgb(255,0,0);">isset(<span style="color:rgb(61,133,198);">$_SESSION</span>[<span style="color:rgb(255,0,0);">&#8220;VariableName&#8221;</span>]) //If this return false, that mean this session is null<br /><span style="color:rgb(255,0,0);">?></p> 

<p>
  </span></span>
</p>

<div>
  <span style="color:rgb(255,0,0);"><span style="color:rgb(255,0,0);"><?php<br /></span><span style="color:rgb(255,0,0);"> <span style="color:rgb(56,118,29);">if</span>(<span style="color:rgb(0,0,255);">isset</span>(<span style="color:rgb(61,133,198);">$_SESSION</span>[<span style="color:rgb(255,0,0);">&#8220;VariableName&#8221;</span>])){<br /> <span style="color:rgb(0,0,255);">echo </span>&#8220;Session value:&#8221; . <span style="color:rgb(61,133,198);">$_SESSION</span>[<span style="color:rgb(255,0,0);">&#8220;VariableName&#8221;</span>];<br /> <span style="color:rgb(61,133,198);">$_SESSION</span>[<span style="color:rgb(255,0,0);">&#8220;VariableName&#8221;</span>] = &#8220;Assigned&#8221;;<br /> }<span style="color:rgb(106,168,79);">else</span>{<br /> <span style="color:rgb(0,0,255);">echo </span><span style="color:rgb(255,0,0);">&#8220;Session is null&#8221;</span>;<br /> }<br /><span style="color:rgb(255,0,0);">?></span><br /><span class="Apple-style-span" style="color:#000000;"><br /></span><span style="background-color:rgb(255,255,255);"><span class="Apple-style-span" style="color:#000000;">If the result is &#8220;</span><b><span class="Apple-style-span" style="color:#000000;">Session is null</span></b><span class="Apple-style-span" style="color:#000000;">&#8220;, once you refresh the page again, it should display &#8220;Session value: Assigned&#8221;.</span></span><span class="Apple-style-span" style="color:#000000;"></p> 
  
  <p>
    If not, that mean the Session feature has not been turn on properly on you server.
  </p>
  
  <p>
    <b>Solution 1:</b><br />If you are allowed to modify the php.ini file, you can open up the &#8220;php.ini&#8221; file and Search for the keyword &#8220;</span>session.auto_start<span class="Apple-style-span" style="color:#000000;">&#8220;<br />To ensure </span>session.auto_start= 1<span class="Apple-style-span" style="color:#000000;">;<br />After you edited it, you can restart the web sever and try again.</p> 
    
    <p>
      <b>Solution 2:</b><br />You can use the follow code to enable the session feature:</span><br /><span style="font-family:Courier New;"><span style="color:rgb(0,0,0);"><span style="color:rgb(0,0,187);">session_start</span><span style="color:rgb(0,119,0);">();</span></span></span>
    </p>
    
    <p>
      <span class="Apple-style-span" style="color:#000000;">Hope you find this useful!</span></span></span></div>