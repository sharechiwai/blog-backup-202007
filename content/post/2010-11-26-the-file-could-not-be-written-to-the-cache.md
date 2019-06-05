---
id: 974
title: 'IE：The file could not be written to the cache &#8212; 在IE 上出現 該文件不能寫入到緩存'
date: 2010-11-26T12:00:17+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=974
permalink: /2010/11/the-file-could-not-be-written-to-the-cache/
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
---
<div id="_mcePaste">
  今天公司的<strong>ASP.Net</strong>網頁上出現了一個問題
</div>

<div id="_mcePaste">
  首先是有客戶[在<strong>IE </strong>中]不能打開一個<strong>xls </strong>的超連結&#8230;
</div>

<div id="_mcePaste">
  我們測試時用<strong>FireFox </strong>和<strong>Google Chrome</strong> 都是沒有問題的
</div>

<div id="_mcePaste">
  之後再用IE 嘗試打開找download 這個File 時出現以下的錯誤信息<br /> &#8220;<span style="color: #ff0000;"><strong>The file could not be written to the cache</strong></span>&#8220;
</div>

[<img class="alignnone size-full wp-image-975" title="CouldNotBeWritten" src="https://i2.wp.com/farm6.static.flickr.com/5247/5687847137_6c0b367e08.jpg?w=625" alt="" data-recalc-dims="1" />  
](https://i2.wp.com/farm6.static.flickr.com/5247/5687847137_6c0b367e08.jpg) 之後發現原因是因為我們公司的網頁是用了SSL 來加密的..  
但是之前為了增加網頁的效能和使用考經驗我們亦都 啟用了 **IIS** 上的 &#8220;E**nable content expiration**&#8221; 設定.. 因為這些文件不會更新得很頻密的關係所以啟動了Cache&#8230;  
很可惜IE 處理和 **SSL**有關的文件的**Cache** 上出現了一些問題&#8230; 所以便出現了這個錯誤句子了

**解決方法**很簡單&#8230;  
就是到**IIS** 上  
把開相關的&#8221;**資料夾內容**&#8220;/ 或&#8221;**Virtual Directory 內容**&#8221;  
之後選擇&#8221;**Header tab**&#8221;  
只要取消選取&#8221;**Enable content expiration**&#8221;  
[<img class="alignnone size-full wp-image-976" title="ClearEnableContentExpiration" src="https://i0.wp.com/farm6.static.flickr.com/5266/5688336554_68079ea8c6.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5266/5688336554_68079ea8c6.jpg)  
Hope you find it useful