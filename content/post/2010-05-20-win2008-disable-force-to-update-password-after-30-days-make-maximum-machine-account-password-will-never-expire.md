---
id: 122
title: 'Win2008 Disable force to update password after 30 days ->Make Maximum machine account password will never expire'
date: 2010-05-20T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/05/20/win2008-disable-force-to-update-password-after-30-days-make-maximum-machine-account-password-will-never-expire
permalink: /2010/05/win2008-disable-force-to-update-password-after-30-days-make-maximum-machine-account-password-will-never-expire/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "7343868555762548403"
categories:
  - Windows Server
---
<div class="separator" style="clear:both;text-align:center;">
</div>

Have been set up a **Virtual PC** and installed **Windows Server 2008** last year and would like to try something in **Windows Server 2008**. However one thing which annoy me is it require me to change my password every **30 days**. That mean I need to use different password every month. The worst thing is I do not think I will login every month, so I cannot remember which password I used before. Finally I find a way to disable the feature in **Windows 2008** for user to change their password every **30 day**.

**Solution:**  
1) Click on &#8220;**Start**&#8221; -> &#8220;**Administrative Tools**&#8221; -> &#8220;**Local Security Policy**&#8220;

<div class="separator" style="clear:both;text-align:center;">
  <a href="http://sharechiwai.files.wordpress.com/2010/05/localsecuritypolicy.jpg" style="margin-left:1em;margin-right:1em;"><img border="0" height="485" src="http://sharechiwai.files.wordpress.com/2010/05/localsecuritypolicy.jpg?w=300&#038;resize=625%2C485" width="625" data-recalc-dims="1" /></a>
</div>



<div class="separator" style="clear:both;text-align:center;">
</div>

2) Inside the &#8220;**Local Security Policy**&#8221; click on &#8220;+&#8221; to Expand &#8220;**Account Policies**&#8220;

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/lsp_passwordpolicy.jpg" style="margin-left:1em;margin-right:1em;"><img border="0" height="305" src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/lsp_passwordpolicy.jpg?resize=625%2C305" width="625" data-recalc-dims="1" /></a>
</div>

3) Click on &#8220;**Password Policy**&#8221; and double Click on &#8220;**Maximum password age**&#8220;

<div class="separator" style="clear:both;text-align:center;">
</div>

4) Then you will see the &#8220;**Maximum password age Properties**&#8221; 

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/maxpasswordage.jpg" style="margin-left:1em;margin-right:1em;"><img border="0" height="640" src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/maxpasswordage.jpg?resize=538%2C640" width="538" data-recalc-dims="1" /></a>
</div>

5) You can set the maximum password age here. The values must be between ****&#8211;**998**.

&#8220;****&#8221; mean the Password will not expire.

If you have better way to achieve that/my concept is not correct, please leave me a message so that I can correct it.

Hope you find it useful.