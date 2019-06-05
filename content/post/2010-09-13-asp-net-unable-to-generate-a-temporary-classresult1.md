---
id: 628
title: Asp.Net Unable to generate a temporary class(result=1)
date: 2010-09-13T05:32:49+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=628
permalink: /2010/09/asp-net-unable-to-generate-a-temporary-classresult1/
jabber_published:
  - "1284327170"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1284991785";}";'
email_notification:
  - "1284327171"
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
---
今日早上收到朋友的Email 說 公司的一個將會發佈的網頁有問題  
當瀏覽到其中一頁時遇到以下的Error Message  
[<img title="Error" src="https://i0.wp.com/farm6.static.flickr.com/5063/5687821903_e064889407.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5063/5687821903_e064889407.jpg)  
**<span style="color: #ff0000;">Unable to generate a temporary class(result=1)<br /> error CS2001: Source file &#8216;C:WINDOWSTEMPxxxx.cs&#8217; could not be found<br /> error CS2008: No inputs specified</span>**

我記得很久之前也遇過差不多的問題

其實解決方法十分簡單  
我們可以跟隨錯誤信息來分析這個問題  
<span style="color: #ff0000;">Unable to generate a temporary class</span>  
和  
<span style="color: #ff0000;">error CS2001: Source file &#8216;C:WINDOWSTEMPxxxx.cs&#8217; could not be found</span>  
加在一起給我的感覺是  
因而不能產生這個 **temporary class**  
所以便找不到這個**Source file**了

不能產生**temporary class** 其中一個原因是  
因為在**Server**上沒有寫的權力&#8230;  
所以我登入到這個**Server** 上  
找到這個路徑  
<span style="color: #ff0000;">&#8220;C:WINDOWSTEMP&#8221;</span>  
更改了 這個**IIS** 的使用者權限  
令他可以修改這個資料夾的權力  
E.g.加入 **Modify/Read/Write**的權力  
便可以解決這個問題了

Hope you find it useful