---
id: 3688
title: 'How to check if User Exist on Linux &#8211; 如何在Linux 上檢查使用者存在'
date: 2016-07-01T00:00:19+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3688
permalink: '/2016/07/how-to-check-if-user-exist-on-linux-%e5%a6%82%e4%bd%95%e5%9c%a8linux-%e4%b8%8a%e6%aa%a2%e6%9f%a5%e4%bd%bf%e7%94%a8%e8%80%85%e5%ad%98%e5%9c%a8/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Linux
  - Linux Command
  - Ubuntu
  - Vagrant
---
最近和朋友建立了一個Sample Project  
來幫自己學習如何建立一個良好的開發環境  
由於六月小弟去了差不多一個月旅遊..  
朋友在有空的時候已經用**Vagrant**建立了一個開發環境  
還有把所有的code 放了在**Bitbucket**上..  
我只要clone 下來之後執行**readme** 入的command 便可以開始開發了&#8230;  
和**username** / **password**

誰不知..小小的問題出現了&#8230;  
不知道為什麼我不能**SSH** 到這一個**vagrant** 的VM上..  
但是在Virtual Box 內只需要輸入 &#8220;**vagrant**&#8220;為使用者便可以登入..  
而**readme**內的 **username/password** 登入時..**linux** 說&#8221;<span style="color: #ff0000;"><strong>Login Incorrect</strong></span>&#8221;

所以便想到登入為&#8221;**vagrant**&#8220;後  
再用指令去查詢

**解決方法**  
我使可以使用 &#8220;<span style="color: #008000;"><strong>getent passwd</strong></span>&#8220;指令  
因為**passwd**存了所有的user info

查看user 使用者 存不存在

<pre>getent passwd userNameHere
getent passwd user1
</pre>

<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8632/28134204122_88bd7e45ee_z.jpg?resize=625%2C187" alt="Linux Check if user exist" width="625" height="187" data-recalc-dims="1" />  
查看**user group** 存不存在  
我使可以使用 &#8220;<span style="color: #008000;"><strong>getent group</strong></span>&#8220;指令到

<pre>getent group groupNameHere
getent group usergroup1
</pre>

<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7649/27957698270_a06cf019fb_z.jpg?resize=625%2C302" alt="Check if user group exist on linux" width="625" height="302" data-recalc-dims="1" />  
如果沒有東西輸出的話..說明了..找不到資料  
Hope you find it useful