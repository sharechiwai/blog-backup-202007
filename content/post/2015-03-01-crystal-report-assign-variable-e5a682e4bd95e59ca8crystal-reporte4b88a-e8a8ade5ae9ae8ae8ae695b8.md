---
id: 3396
title: 'Crystal Report Assign Variable &#8211; 如何在Crystal Report上 設定變數'
date: 2015-03-01T00:00:04+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3396
permalink: '/2015/03/crystal-report-assign-variable-%e5%a6%82%e4%bd%95%e5%9c%a8crystal-report%e4%b8%8a-%e8%a8%ad%e5%ae%9a%e8%ae%8a%e6%95%b8/'
categories:
  - Crystal Report Tips and Tricks
tags:
  - Crystal Report
---
由於太耐沒有使用crystal report的關係  
所以忘了怎樣 **Assign variable**/**設定變數**  
通常**Developer**都會使用&#8221;**=**&#8220;去 **Assign variable**/**設定變數**  
今天也嘗試使用 &#8220;**=**&#8221; 來 **Assign Variable** 可惜得到不到想要的結果

最後發現原來是**syntax**上用錯了  
以下是正確的方法 &#8220;**:=**&#8221;  
要**assign variable**我們耐要使用 &#8220;**:=**&#8220;的

E.G.  
**錯誤示範**

<pre>// Define Variable
StringVar s = "abc";
// Show Variable
s
</pre>

<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8571/16526846020_9c46957d8a_z.jpg?resize=459%2C349" alt="Crystal Report - Formula Workshop - Formula Editor Failed to assign Variable Sample" width="459" height="349" data-recalc-dims="1" />  
**結果**是沒有任何寫出現的

在**Crystal Report** 上**Assign Variable**的正確方法是使用 &#8220;**:=**&#8221;

<pre>// Define Variable
StringVar s := "abc";
// Show Variable
s
</pre>

<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8651/16506977947_997b429bbd_z.jpg?resize=476%2C352" alt="Crystal Report - Formula Workshop - Formula Editor Success to assign Variable Sample" width="476" height="352" data-recalc-dims="1" /> 

這個Demo **Designer View**的 **Preview**  
<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8562/16712979531_78eed9e3f4_z.jpg?resize=600%2C246" alt="Crystal Report Designer Mode Preview - How to assign Variable" width="600" height="246" data-recalc-dims="1" /> 

這個**Demo**的 **Preview**  
<img class="alignnone" src="https://i1.wp.com/farm9.static.flickr.com/8590/16713200702_04cc3b3488_z.jpg?resize=350%2C240" alt="Crystal Report - Preview Mode - How to assign Variable" width="350" height="240" data-recalc-dims="1" /> 

Hope you find it useful