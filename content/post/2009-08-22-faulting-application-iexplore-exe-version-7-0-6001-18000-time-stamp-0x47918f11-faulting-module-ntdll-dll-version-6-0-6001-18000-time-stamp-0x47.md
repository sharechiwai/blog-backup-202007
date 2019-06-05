---
id: 374
title: Faulting application iexplore.exe, version 7.0.6001.18000, time stamp 0x47918f11, faulting module ntdll.dll, version 6.0.6001.18000, time stamp 0x47
date: 2009-08-22T08:22:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/22/faulting-application-iexplore-exe-version-7-0-6001-18000-time-stamp-0x47918f11-faulting-module-ntdll-dll-version-6-0-6001-18000-time-stamp-0x47
permalink: /2009/08/faulting-application-iexplore-exe-version-7-0-6001-18000-time-stamp-0x47918f11-faulting-module-ntdll-dll-version-6-0-6001-18000-time-stamp-0x47/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "2770388325603866028"
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
Something weird happened on my IE7 after I updated the Flash Player this morning.  
Whenever I try to load up IE, the Internet Explorer will start up, but the status shown as &#8220;<span style="font-weight:bold;">Connecting</span>&#8220;. After a while a popup message come up and say, IE7 crashed, do you want to debug or something like that.

<span style="color:rgb(255,0,0);font-size:85%;"><span style="font-weight:bold;"><<br /><span style="font-weight:bold;">6.0.6001.18000, time stamp 0x4791a7a6, exception code 0xc0000005, fault offset 0x0002afed, process id 0x144c, application start </span><br /><span style="font-weight:bold;">time 0x01c9a9f3d2013aef</span></span><span style="color:rgb(255,0,0);">. >></span><br /><span style="color:rgb(0,0,0);">IE7 crashed in Vista &#8211; Not responding.</span></p> 

<p>
  <span style="color:rgb(0,0,0);">When I check the Event Log, I found the following Error message.</span>
</p>

<p>
  <span style="color:rgb(0,0,0);">I have tried several ways and see if I can solve the problem.</span><br /><span style="color:rgb(0,0,0);">1) Restart my Computer <- did not work. 2) Clean all Temp File <- did not work. 3) Try to re-install IE7 by going to Microsoft website; unfortunately it said IE7 is already come with Windows Vista, therefore I cannot download it again to re-install it. I did think about to install IE8 instead&#8230; Finally I worked out how to solve that problem properly. Here it is the solution. 1) Right click on the IE7 icon and select "</span><span style="font-weight:bold;color:rgb(0,0,0);">Run as Administrator</span><span style="color:rgb(0,0,0);">&#8221; (Although IE7 cannot load up properly if you just double click on the icon to start it up. It does work when you run it as administrator)</span>
</p>

<p>
  <span style="color:rgb(0,0,0);">2) Click on &#8220;</span><span style="font-weight:bold;color:rgb(0,0,0);">Tools</span><span style="color:rgb(0,0,0);">&#8221; on the menu bar and Select &#8220;</span><span style="font-weight:bold;color:rgb(0,0,0);">Internet Options</span><span style="color:rgb(0,0,0);">&#8220;</span><br /><span style="color:rgb(0,0,0);">3) Click on &#8220;</span><span style="font-weight:bold;color:rgb(0,0,0);">Advanced</span><span style="color:rgb(0,0,0);">&#8221; Tab</span><br /><span style="color:rgb(0,0,0);">4) You will see a &#8220;</span><span style="font-weight:bold;color:rgb(0,0,0);">Reset&#8230;</span><span style="color:rgb(0,0,0);">&#8221; button in the bottom of the page. </span><img src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/f49318930c71400f98de3c3807354dea" height="523" width="423" /><br /><span style="color:rgb(0,0,0);">5) and Click on it, a pop-up box will be display and let you know what is going to happen if you reset your Internet Explorer settings.</span><br /><img src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/ee0d5c576a0245bd9024fad016e82b03" height="296" width="481" /><br /><span style="color:rgb(0,0,0);"><span>6) Click &#8220;reset&#8221;<br />7) Once it is done. You can try to run IE7 again. It should works.</p> 
  
  <p>
    Good Luck.
  </p>
  
  <p>
    Hope you find it useful.</span></span></span>
  </p>