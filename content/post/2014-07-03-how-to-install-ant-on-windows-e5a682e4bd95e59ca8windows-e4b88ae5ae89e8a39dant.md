---
id: 3264
title: 'How to install Ant on Windows &#8211; 如何在Windows 上安裝Ant'
date: 2014-07-03T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3264
permalink: '/2014/07/how-to-install-ant-on-windows-%e5%a6%82%e4%bd%95%e5%9c%a8windows-%e4%b8%8a%e5%ae%89%e8%a3%9dant/'
categories:
  - Ionic Framework
tags:
  - Apache Ant
  - ionic troubleshooting
  - troubleshooting
---
在安裝/設定/使用**Ionic Framework** 其間  
需要安裝 **Apache Ant** 來**Build** 某些東西..  
如果沒有**安裝**/**設定** 好 **Ant**的話..  
當你使用 **Ionic**時便會出現一些錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Executing command &#8216;ant&#8217;, make sure you have ant installed and added to your path</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm6.static.flickr.com/5553/14820711775_231686ff1c_z.jpg?resize=625%2C181" alt="Executing command 'ant', make sure you have ant installed and added to your path" width="625" height="181" data-recalc-dims="1" /> 

如何在**Windows** 上安裝 **Apache Ant**?

**解決方法十**分簡單  
我們可以到以下網址下載最新的**Ant**  
<a title="Apache Ant Download Link" href="http://ant.apache.org/bindownload.cgi" target="_blank">http://ant.apache.org/bindownload.cgi</a>  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5572/14797717876_451043ff47_z.jpg?resize=625%2C222" alt="Download Apache Ant" width="625" height="222" data-recalc-dims="1" /> 

由于我是用**Windows**系統..所以下載zip檔案比較適合  
之後把檔案解壓縮到一個地方  
我解壓縮到&#8221;<span style="color: #008000;"><strong>D:\Software\apache-ant</strong></span>&#8220;這個資料夾上  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3918/14820352002_66b0e85342_z.jpg?resize=625%2C325" alt="My Ant Folder Path" width="625" height="325" data-recalc-dims="1" /> 

在電腦的**Environment Variable** 上加入這個**Ant**的資料夾的路徑

E.g.  
去電腦的內容  
<img class="alignnone" src="https://i2.wp.com/farm3.static.flickr.com/2918/14634050659_346e83b42a_z.jpg?resize=625%2C244" alt="System -> Control Panel -> All Control Panel Items " width="625" height="244" data-recalc-dims="1" />  
按一下&#8221;**Advanced System Settings**/**進階系統設定**&#8221; -> &#8220;**Advanced** tab/**進階** 分頁&#8221; ->&#8221;**Environment Variables** / **環境變數**&#8221; 按一下

<img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3843/14818343754_8cbbbf8c32_z.jpg?resize=562%2C580" alt="Environment Variables" width="562" height="580" data-recalc-dims="1" />  
在&#8221;**System variable** / **系統變數**&#8221; 上新增 &#8220;**ANT_HOME**&#8221;  
之後在**Variable name**上輸入&#8221;**ANT_HOME**&#8221;  
**&#8220;Variable Value&#8221;** 加上  
你解壓縮了的**Ant** 的資料夾的路徑  
E.G. 我的**Ant** 路徑是  
&#8220;<span style="color: #008000;"><strong>D:\Software\apache-ant</strong></span>&#8221;  
完成後按&#8221;**OK** / **確定**&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3914/14798043756_a3745705c6_z.jpg?resize=459%2C537" alt="Environment Variable -> Edit System Variable" width="459" height="537" data-recalc-dims="1" /> 

之後選擇&#8221;**System variable** / **系統變數**&#8221; 上的 &#8220;**path**&#8221;  
在最後一段文字上輸&#8221;<span style="color: #008000;"><strong>;%ANT_HOME%/bin</strong></span>&#8221;  
這會使用你之前定義的**ANT_HOME**變數再加bin 來話給電腦聽你的**ant bin** 在那裡  
<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3898/14634487727_16bd843389_z.jpg?resize=459%2C537" alt="Apache Ant Bin Folder" width="459" height="537" data-recalc-dims="1" />  
之後可以在**Command Prompt**輸入  
ant  
看看有沒有和**ant**相關的**command**出現

雖然是有錯誤..但是已經不是出現  
&#8220;<span style="color: #ff0000;"><strong>&#8216;ant&#8217; is not recognized as an internal or external command. operable program or batch file</strong></span>&#8221;  
所以可以說**Ant**已經設定好了一部分

在將來的網誌裡會和大家分享怎樣解決其實設定**Ant**時出現的問題

Hope you find it useful