---
id: 183
title: 'ArgumentNullException was unhandled &#8212; Parameter name: activationContext'
date: 2010-04-25T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/04/25/argumentnullexception-was-unhandled-parameter-name-activationcontext
permalink: /2010/04/argumentnullexception-was-unhandled-parameter-name-activationcontext/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "7797997628273942295"
categories:
  - .Net Tips And Tricks
---
After upgrading application from **VS2010 RC** to **VS2010 RTM**, my application stop working. I started to receive the error below, when I try to run/debug my application.

<span style="color:#ff0000;">&#8220;<strong>ArgumentNullException was unhandled</strong>&#8220;<br style="color:red;" /><strong>Value cannot be null.<br /> Parameter name: activationContext</strong></span>

<div class="separator" style="clear:both;text-align:center;">
  <a style="margin-left:1em;margin-right:1em;" href="http://sharechiwai.files.wordpress.com/2010/04/argumentnullexception.png"><img src="http://sharechiwai.files.wordpress.com/2010/04/argumentnullexception.png?w=300&#038;resize=400%2C251" border="0" alt="" width="400" height="251" data-recalc-dims="1" /></a>
</div>

After doing some research online. I have found the solution.

**Solution**

  1. Go to your project properties [Double click on &#8220;**My Project**&#8220;].
  2. Click on the &#8220;**Security**&#8221; tab
  3. **Un-tick** the check-box for &#8220;**Enable ClickOnce security settings**&#8220;

<div class="separator" style="clear:both;text-align:center;">
  <a style="margin-left:1em;margin-right:1em;" href="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/securityenableclickoncesecuritysettings.png"><img src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/securityenableclickoncesecuritysettings.png?resize=625%2C279" border="0" alt="" width="625" height="279" data-recalc-dims="1" /></a>
</div>

Then try to run your application again. It should work fine.

Hope you find it useful.