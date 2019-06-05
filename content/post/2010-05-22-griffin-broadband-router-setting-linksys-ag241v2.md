---
id: 120
title: Griffin Broadband Router Setting Linksys AG241V2
date: 2010-05-22T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/05/22/griffin-broadband-router-setting-linksys-ag241v2
permalink: /2010/05/griffin-broadband-router-setting-linksys-ag241v2/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "792300196197551220"
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
I had a problem on using Router connect to the Internet today. When I try to check the router settings, I have discovered the disaster has happened. I found that all the router setting is gone. I remember it did take me a while to set up the ADSL connection by using Router. It is not as straight forward as the other ISP.(The ISP is Griffin Broadband.)

Fortunately, I still has a USB modem which I can use to connect to the Internet. [and try to complete the  
data transfer process at work and solve the router problem].

Finally I have worked out how to config the router to connect to Griffin Broadband.

Here it is the configuration.

On Encapsulation Select &#8220;**RFC 2364 PPPoA**&#8220;  
Multiplexing: &#8220;**LLC**&#8220;  
Qos Type &#8220;**UBR**&#8221; or it can be anything.  
The important part,which I have struggle with is &#8220;**Virtual Circuit**&#8221; part  
Your would need to **disable &#8220;Autodetect&#8221;**  
Then change **VCI** to &#8220;**38**&#8220;  
You can leave **DSL Modultion** as &#8220;**MultiMode**&#8220;  
Then fill in your &#8220;**Username**&#8221; and &#8220;**Password**&#8220;  
Finally click on the &#8220;**Save Settings**&#8221; Button.

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/adslsettings.jpg" style="margin-left:1em;margin-right:1em;"><img border="0" height="516" src="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/adslsettings.jpg?resize=625%2C516" width="625" data-recalc-dims="1" /></a>
</div>

 If your username/password and telephone line is ok. You should be able to access internet.

Hope this could Help!  
Good Luck