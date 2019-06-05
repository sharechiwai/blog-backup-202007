---
id: 929
title: 'ASP.Net IIS Browser Image Cache Issue &#8212; 在ASP.Net 中解決Cache 了的圖片不能更新使用新的圖片問題'
date: 2010-11-22T00:00:46+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=929
permalink: /2010/11/asp-net-iis-browser-image-cache-issue/
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
---
最近都是忙公司的網站&#8230;  
為了提升使用者體驗  
我們嘗試使用**IIS** 中的**Caching**,  
希望使用者不同每次都需要**Download** 這網站的圖或**CSS** 檔&#8230;  
這可以令瀏覽速度加快

之後我們也建立了一些**Virtual Directory**用來儲存一些每天都會更新的圖片&#8230; 其實是從**Google Chart** 上**download** 來的..因為公司的網站用了SSL &#8230;所以每當有需要連線到其他的domain website 時 在**IE**上總會出現一些令人煩惱的信息&#8230;  
所以最後選擇了每天**Download**這些圖片&#8230;之後再用ASP.Net 來連接這想在**Virtual Directory** 上的圖&#8230;

誰不知&#8230; 這些圖片不懂得自動更新&#8230;即使檔案的修改日期已經更新了..但是在客戶端都只是看到之前的圖&#8230;  
最後發現&#8230;原來這個**Virtual Directory**是繼承了這個**Web Application** 的 **Cache [content expiration] settings**

解決方法很想十分簡單&#8230;  
只要在這個&#8221;**Virtual Directory/虛擬目錄**&#8221; 上選擇&#8221;**Properies/內容** &#8221;  
之後選&#8221;**HTTP Header&#8217;** 分頁  
之後選&#8221;**Enable content expiration**&#8221;  ->選&#8221;**Expire immediately**&#8220;便可&#8230;  
[<img title="IISCache" src="https://i1.wp.com/farm6.static.flickr.com/5265/5687868213_d91ce544ed.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5265/5687868213_d91ce544ed.jpg)  
很可惜用戶已經瀏覽過公司的網站&#8230;  
所以他們的瀏覽器上有了這個 **Cache Expiration** 設定&#8230;  
瀏覽器只會在**Cache** 過期後才會再次**Load** 這個檔案的&#8230;  
用戶可以按&#8221;**CTRL**&#8221; + &#8220;**F5**&#8221; 去解決這個問題&#8230;  
但是如果需要找每一個用戶去做這個動作..給別人的感覺很不專業&#8230;

最後我們找到了解決的方法..  
便是我們在圖片的**URL** 上加了一個用**timestamp** 做成的**Query string**  
E.G.  <http://i1255.photobucket.com/albums/hh631/sharechiwai/temporary-1.jpg?20101118000000>

由於這個圖片的URL不同了..所以瀏覽器便會感到這是一個新的圖片檔案名&#8230;  
便不會從**Cache**中 load 這個圖片出來了 =)

Hope you find it useful