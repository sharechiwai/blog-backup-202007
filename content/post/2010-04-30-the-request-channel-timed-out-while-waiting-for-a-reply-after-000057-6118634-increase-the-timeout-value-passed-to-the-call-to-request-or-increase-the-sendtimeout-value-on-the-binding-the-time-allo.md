---
id: 170
title: The request channel timed out while waiting for a reply after 00:00:57.6118634. Increase the timeout value passed to the call to Request or increase the SendTimeout value on the Binding. The time allotted to this operation may have been a portion of a longer timeout.
date: 2010-04-30T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/04/30/the-request-channel-timed-out-while-waiting-for-a-reply-after-000057-6118634-increase-the-timeout-value-passed-to-the-call-to-request-or-increase-the-sendtimeout-value-on-the-binding-the-time-allo
permalink: /2010/04/the-request-channel-timed-out-while-waiting-for-a-reply-after-000057-6118634-increase-the-timeout-value-passed-to-the-call-to-request-or-increase-the-sendtimeout-value-on-the-binding-the-time-allo/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "7537504960799539031"
categories:
  - .Net Tips And Tricks
  - WCF
  - Web Services
---
I am working on a application, which need to consume a web-service which is provided by another company. When I try to make a **Web-service request/<span class="goog-spellcheck-word" style="background:none repeat scroll 0 0 yellow;">RPC</span>** call, I have received a **timeout exception** from my application.  
&#8220;<span style="color:red;font-size:x-small;"><b>The request channel timed out while waiting for a reply after 00:00:57.6118634. Increase the timeout value passed to the call to Request or increase the Timeout value on the Binding. The time allotted to this operation may have been a portion of a longer timeout.</b></span>&#8220;

I guess, it is something to do with their web-service, E.g. the web service did not work properly and it used to work in **Visual Studio 2005** [I am using **Visual Studio 2008** for this application]. When I check the application <span class="goog-spellcheck-word" style="background:none repeat scroll 0 0 yellow;">config</span> file. I have found something interesting, which is related with timeout. Then I have figured out what is causing the **timeout exception**. =).

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i0.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/wstimeout0100.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="267" src="https://i0.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/wstimeout0100.png?resize=625%2C267" width="625" data-recalc-dims="1" /></a>
</div>

<span id="goog_165517558"></span><span id="goog_165517559"></span>  
**Here it is my solution:**  
To resolve the **timeout exception**, you can simply increase the timeout value to a appropriate time, which will not affect the performance of your application. E.g. If you set the timeout value too high, when the web-service do gone down, your application will waste lots of time, because it think the web-service is doing something.

For my application, I have updated the timeout value to 3 minutes which is **00:03:00**. [**<span class="goog-spellcheck-word" style="background:none repeat scroll 0 0 yellow;">hh</span><span style="background-color:yellow;">:mm:</span><span class="goog-spellcheck-word" style="background:none repeat scroll 0 0 yellow;">ss</span>**].

<div class="separator" style="clear:both;text-align:center;">
  <a href="http://sharechiwai.files.wordpress.com/2010/04/wstimeout0300.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="254" src="http://sharechiwai.files.wordpress.com/2010/04/wstimeout0300.png?w=300&#038;resize=625%2C254" width="625" data-recalc-dims="1" /></a>
</div>

Hope you find it useful. =)