---
id: 1684
title: 'mstsc Remote Desktop Shut down computer &#8211; 在遠端桌面服務 中關機或重新開啟電腦'
date: 2011-03-31T00:00:27+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1684
permalink: '/2011/03/mstsc-remote-desktop-shut-down-computer-%e5%9c%a8%e9%81%a0%e7%ab%af%e6%a1%8c%e9%9d%a2%e6%9c%8d%e5%8b%99-%e4%b8%ad%e9%97%9c%e6%a9%9f%e6%88%96%e9%87%8d%e6%96%b0%e9%96%8b%e5%95%9f%e9%9b%bb%e8%85%a6/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
最近使用**Remote Desktop/遠端桌面服務**時 發現了一個問題..  
就是沒有了**關機/電腦重啟**這個功能&#8230;  
有時候需要使用 **Remote Desktop**幫助公司設定電腦時會有需要重新啟動電腦的..  
E.G. 安裝軟體時或其他種種的原因..  
但是當你使用**Remote Desktop**登入了電腦後  
受控制的電腦只有&#8221;**登出/LogOff**&#8221; 和&#8221;**離線/Disconnect**&#8221; 兩個選擇給大家  
[<img class="alignnone" title="Remote Desktop Logoff function" src="https://i1.wp.com/farm6.static.flickr.com/5261/5662084707_573e8d40b4.jpg?resize=447%2C153" alt="" width="447" height="153" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5261/5662084707_573e8d40b4.jpg)  
如果大家可 使用**關機/電腦重啟**這個功能

大家可以使用**Command Prompt** 輸內指令來令到電腦關機或重新啟動..  
E.G.  
按一下&#8221;**開始**&#8220;->&#8221;**執行**&#8221; ->輸入&#8221;**cmd**&#8221; 之後按&#8221;**Enter**&#8221;  
輪入> &#8220;<span style="color: #008080;"><strong>shutdown -r -t 60</strong></span>&#8221;  
這會令到你的電腦在1分鐘後重新啟動  
輪入> &#8220;<span style="color: #008080;"><strong>shutdown -s -t 60</strong></span>&#8221;  
這會令到你的電腦在1分鐘後關機

**另外一個更好的方法是**  
按下&#8221;**CTRL**&#8220;+ &#8220;**ALT&#8221;** + &#8220;**End**&#8221;  
這便可以打開受控制中的電腦的**Task Manager**..  
之後我們便可以選擇**關機**或**重新啟動**了..  
[<img class="alignnone" title="Task manager" src="https://i0.wp.com/farm6.static.flickr.com/5021/5662654368_1641ef6a74.jpg?resize=500%2C244" alt="" width="500" height="244" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5021/5662654368_1641ef6a74.jpg)

Hope you find it useful