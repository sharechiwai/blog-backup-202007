---
id: 371
title: Cannot connect to Internet after connecting VPN?
date: 2009-08-26T08:26:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/26/cannot-connect-to-internet-after-connecting-vpn
permalink: /2009/08/cannot-connect-to-internet-after-connecting-vpn/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "8654324704420879448"
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
Not sure if it happened to you after you connect your PC to your Company/School network via VPN.

When I was in Uni, sometime I have to connect VPN in order to download from/submit assessment to University network. After I setup VPN on my computer. My MSN/ICQ and Internet seems to get disconnected. I can only see the university web site and the **network drive** on the University Network.

I thought that is the only way that VPN work. Until a year after, one of my project team-mate teach me how to solve that issue.

It is quite straight forward.

Here it is the step that can help you solve this Issue.

1) You can set up the VPN connect by follow the uni./Company&#8217;s instruction.

2) Once you&#8217;ve setup the VPN connection you can do the following.

3)Go to &#8220;**Start**&#8221; menu &#8211;> &#8220;**Connect To**&#8220;

4) Right click on the **Connection** that you want to connect to and select &#8220;**Properties**&#8220;.  
<img title="Connecton Properties" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/4f2a52bff683463f9e547be26fa599d8" alt="Connecton Properties" height="425" width="365" />  
5) Select &#8220;Internet Protocol (TCP/IP)&#8221;  
6) Then click on &#8220;Properties&#8221; button

<img title="Internet Protocol (TCP/IP) Properties" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/f99f4c66ef8645ad893ab913ba7da54a" alt="Internet Protocol (TCP/IP) Properties" height="455" width="404" /> 

7) Click on the &#8220;**Advanced**&#8221; button  
You will then see the &#8220;**Advanced TCP/IP Settings**&#8221; windows as below.

<img title="Advanced TCP/IP Settings" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/d2e7aa7496f54eea9f319c9551f5aa34" alt="Advanced TCP/IP Settings" height="488" width="404" /> 

8) On the &#8220;**General Tab**&#8220;  
**Un-check** the option &#8220;**User default gateway on remote network**&#8220;  
Then click on &#8220;**OK**&#8220;

Once you done it, You can try to connect to the **VPN** again, and see if it works.

This time **MSN**/**ICQ**/ all other applications should still stay online.

Good Luck