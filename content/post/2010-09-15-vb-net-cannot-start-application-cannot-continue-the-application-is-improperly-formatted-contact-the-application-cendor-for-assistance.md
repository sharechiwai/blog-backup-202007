---
id: 631
title: 'VB.Net Cannot Start Application &#8212; Cannot continue. The application is improperly formatted. Contact the application vendor for assistance.'
date: 2010-09-15T09:15:45+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=631
permalink: /2010/09/vb-net-cannot-start-application-cannot-continue-the-application-is-improperly-formatted-contact-the-application-cendor-for-assistance/
jabber_published:
  - "1284536669"
email_notification:
  - "1284536670"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1284991758";}";'
categories:
  - .Net Tips And Tricks
---
今天有位同事向我說有一個我寫的應用程式當他打開時出現錯誤  
<span style="color: #ff0000;"><strong>Cannot continue. The application is improperly formatted. Contact the application vendor for assistance.</strong></span>  
[<img class="alignnone size-full wp-image-632" title="CannotStart" src="https://i2.wp.com/farm6.static.flickr.com/5223/5688389976_e8ba525ba5.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5223/5688389976_e8ba525ba5.jpg)  
由於我之前重新發報過這個應用程式到另一個網絡地址&#8230;所以我便再一次發報了..  
之後還是有同一個錯誤出現..

之後按了一下Details去看看什麼原因

<span style="color: #ff0000;">ERROR SUMMARY<br /> Below is a summary of the errors, details of these errors are listed later in the log.<br /> * Activation of \NetworkLocationShareChiWaiApp.application resulted in exception. Following failure messages were detected:<br /> + Exception reading manifest from file://NetworkLocation/ShareChiWaiApp.application: the manifest may not be valid or the file could not be opened.<br /> + <strong>Manifest XML signature is not valid.</strong></span>  
<span style="color: #ff0000;">+ <strong>No signature was present in the subject.</strong></span>

由於我多數發報的應用程式都是In-house使用的  
所以我都用弓**ClickOnce Publish**的方式發報..  
最後發現了&#8230;

<span style="color: #ff0000;">+ Manifest XML signature is not valid.<br /> + No signature was present in the subject.</span>

這兩句信息應該解釋了其中的一些問題  
由於這個應用是發報在公司的網絡上所以是應該要簽署這個**ClickOnce manifests**的  
**解決方法:**  
開啟 **&#8220;My Project**&#8221;  
之後去 **Signing tab [簽署]分頁** &#8211;>如果**&#8220;Sign the ClickOnce manifests&#8221;** 沒有**tick**的話 便選擇他  
你可能需要建立一個證書的  去簽署這個**ClickOnce manifests**  
按一下 &#8220;**Create Test Certificate**&#8221; 之後輸入密碼便可  
[<img class="alignnone size-full wp-image-633" title="Sign" src="https://i2.wp.com/farm6.static.flickr.com/5247/5687827871_68fdefb952.jpg?w=625" alt="" data-recalc-dims="1" />](https://i2.wp.com/farm6.static.flickr.com/5247/5687827871_68fdefb952.jpg)  
Sign 了這個**ClickOnce manifests** 得他便得到了一個  
更有用的錯誤信息..  
原來他的電腦沒有安裝**.Net 4 Framework**

所以便收到了**<span style="color: #ff0000;">The application is improperly formatted</span>**的錯誤了

Hope you find it useful