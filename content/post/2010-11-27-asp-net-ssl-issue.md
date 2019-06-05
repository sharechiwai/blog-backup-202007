---
id: 813
title: 'ASP.NET SSL Issue &#8211; IE 上的SSL 問題'
date: 2010-11-27T00:00:06+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=813
permalink: /2010/11/asp-net-ssl-issue/
categories:
  - ASP.Net Tips and Tricks
---
最近公司建立了一個新的網站..  
提供一個介面給客戶更新資料..  
最初的我們沒有使用**SSL** 的&#8230;  
由於有些資料是一些敏感性的資料  
所以需要使用**SSL** 來把資料加密

這個網頁有些功能是使用**Google Chart API** 的  
所以有一些圖的**URL** 是連接到不是同一Domain 的 URL. E.G.  Google  
還有..這個網站也有使用**JQuery**的..  
而我們使用的是在**Google** 寄存的 **JQuery Library**  
[以減輕經路的負荷&#8230;]  
誰不知..加了SSL 後的網站..在IE的底下便出了一個問題&#8230;  
每當開啟一些網頁有和連接到不是本地的URL/ E.G. 網外的URL 時  
便會出現以下信息  
&#8220;<span style="color: #ff0000;"><strong>Do you want to view only the webpage content that was delivered securely?</strong></span>&#8221;

<img title="Do You want to view only the webpage content that was delivered securely?" src="https://i0.wp.com/farm5.static.flickr.com/4091/5113207179_7fc551cfac.jpg?resize=466%2C175" alt="Do You want to view only the webpage content that was delivered securely?" width="466" height="175" data-recalc-dims="1" /> 

感到十分煩惱&#8230;  
之後發現解決放法有2個.. 一是改變IE 的設定..二是改變這個網站的編寫方法

**解決方法**  
1) **更變IE 設定**  
可以在IE上的**Menu bar** 上按 &#8220;**Tools**&#8221;  -> &#8220;**Internet Options** &#8221;  
在&#8221;**Internet Options**&#8221; windows 按一下 &#8220;**Security 安全**&#8220;分頁  
之後按一下&#8221;**Custom Level &#8230; 自定級別&#8230;**&#8220;按鈕  
在&#8221;安會設定&#8221; 找 &#8220;**Display mixed content**&#8221;  
把他設定為&#8221;**Enable**&#8221; 之後按&#8221;OK&#8221; 便可  
[<img class="alignnone size-full wp-image-1067" title="AllowMixMode" src="https://i1.wp.com/farm6.static.flickr.com/5022/5688398466_b0791b05b7.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5022/5688398466_b0791b05b7.jpg)

[由於公司有很多使用者&#8230;要他們改變他們的 IE 設定給他們的感覺很不專業&#8230;所以我們便想了另一個解決方法]

2) **改變網站的設計**&#8230;  
預先Download 所有向外又不是**HTTPS** 的 URL 連結用的資源到**IIS Server** 上  
我們寫了一個方法先把**Google Chart API** 生產出來的圖Download 到Server 上之後再把他連到**ASP.Net** 網頁上  
和把寄存在網上的**javascript 和css** 檔案都Download 到一個資料夾上使用  
Hope you find it useful