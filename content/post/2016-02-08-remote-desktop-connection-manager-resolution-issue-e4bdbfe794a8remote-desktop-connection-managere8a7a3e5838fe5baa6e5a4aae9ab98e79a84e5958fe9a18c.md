---
id: 3581
title: 'Remote Desktop Connection Manager Resolution Issue &#8211; 使用Remote Desktop Connection Manager解像度太高的問題'
date: 2016-02-08T00:00:24+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3581
permalink: '/2016/02/remote-desktop-connection-manager-resolution-issue-%e4%bd%bf%e7%94%a8remote-desktop-connection-manager%e8%a7%a3%e5%83%8f%e5%ba%a6%e5%a4%aa%e9%ab%98%e7%9a%84%e5%95%8f%e9%a1%8c/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Remote Desktop
  - Remote Desktop Connection Manager
  - Surface Pro 4
---
自從轉了使用**Surface Pro 4** 之後便  
發現使用**Remote Desktop Connection Manager** **連接到公司的電腦時**  
由於**Surface Pro 4**的解析度很高  
remote 到公司的螢光幕 顯示得很細  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1541/24929672991_0a96a7ac9f_z.jpg?resize=625%2C299" alt="Remote Desktop Connection Manager High Resolution " width="625" height="299" data-recalc-dims="1" />  
很多時候看字時都會感到很吃力..

同事嘗試把顯示加多到**150%**看看能不能解決問題  
<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1552/24957329535_10f71f4be7_z.jpg?resize=625%2C311" alt="Display 150%" width="625" height="311" data-recalc-dims="1" />  
可惜**Remote Desktop Connection Manager** 沒有理會Remote的**Client Workstation的設定**  
當我登入後**還是用很高的解析度去控制電腦**

因為太困擾的關係  
所以便努力research看看有沒有解決方法了

**解決方法**:  
我們只需要更改 **Remote Desktop Connection Manager** 的 **Compatibility**/**兼容性設定**  
在**Remote Desktop Connection Manager  **上按右鍵..選擇&#8221;**內容**/**Property**&#8221;

之後選擇 &#8220;**Compatibility**/**兼容性**&#8221; 分頁  
去**勾去掉** **Disable display scaling on high DPI setting** 便可以了  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1653/24276053973_72a4e33140_z.jpg?resize=361%2C505" alt="Remote Desktop Connection Manager Property -> Compability Disable display scaling on high DPI setting" width="361" height="505" data-recalc-dims="1" />  
按**OK**/**確定**之後  
再次連接**Remote Desktop** 解析度問題應該便解決了  
<img class="alignnone" src="https://i1.wp.com/farm2.static.flickr.com/1481/24661836210_7fdaaf3871_z.jpg?resize=625%2C453" alt="Solve Resolution Issue on Remote Desktop Connection Manager" width="625" height="453" data-recalc-dims="1" /> 

Hope you find it useful