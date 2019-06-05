---
id: 2784
title: 'Logoff / Change Account on TFS Service in Visual Studio 2012 &#8211; 在Visual Studio 2012 上使用火同的TFS 用戶戶口登入TFS Service'
date: 2013-04-20T00:00:20+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2784
permalink: '/2013/04/logoff-change-account-on-tfs-service-in-visual-studio-2012-%e5%9c%a8visual-studio-2012-%e4%b8%8a%e4%bd%bf%e7%94%a8%e7%81%ab%e5%90%8c%e7%9a%84tfs-%e7%94%a8%e6%88%b6%e6%88%b6%e5%8f%a3%e7%99%bb/'
categories:
  - Team Foundation Server
tags:
  - TFS Services
  - Visual Studio 2012
---
今天在**Visual Studio 2012** 嘗試**Check-in** 一個**Project**的 **Source Code** 到**TFS Service**的時  
出現了一些問題&#8230;我正在登入的 **TFS**/ **Microsoft Account** 沒有權限去**Check-in** 程式碼到**TFS Service**上.. 還記起之前因為嘗試 **Windows Azure**的關係..使用了另一個使用者登入 **Visual Studio** 上的**TFS Service**.

現在當我嘗試在&#8221;**Connect To Team Foundation Server**&#8221; 上登出現在使用 **TFS Service**的**Account**用戶.. 之後再次登入..  
很可惜..可能之前選擇了記住密碼 和自動登入..  
所以當我按下登入時&#8230;他便自己登入之前的 **使用者Account**..  
嘗試了很多次和從新啟動電腦也是一樣&#8230;  
[<img class="alignnone size-full wp-image-2788" alt="TFS Auto Sign-in" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/TFS-AutoSigin.png?resize=625%2C568" width="625" height="568" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/TFS-AutoSigin.png)

最後終於想到了解決方法了:

**解決方法**:  
由於**Visual Studio** 之前是以 **IE Windows** 來登入**TFS Services**的  
所以我便嘗試開啟 **IE**..  
之後按下&#8221;**Safety**/**安全**&#8221; ->**&#8220;Delete Browsing History**&#8230;/ **刪除瀏覽歷史**&#8230;&#8221;  
[<img class="alignnone size-full wp-image-2787" alt="Delete Browsing History" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/DeleteBrowsingHistory.png?resize=625%2C320" width="625" height="320" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/DeleteBrowsingHistory.png)  
在&#8221;**Delete Browsing History Dialogue**&#8230;/ **刪除瀏覽歷史視窗**&#8230;&#8221;  
上記住選擇&#8230;刪除&#8221;**Form Data** / **表單數據**&#8221; 和 &#8220;**Password** / **密碼**&#8221;  
[<img class="alignnone size-full wp-image-2786" alt="Delete Browsing History Settings" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/DeleteBrowsingHistorySettings.png?resize=468%2C673" width="468" height="673" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/DeleteBrowsingHistorySettings.png)  
之後按下 &#8220;**確定**/**OK**&#8221;

之後回到**Visual Studio** 的 &#8220;**Connect To Team Foundation Server**&#8221; 再之登出登入 **Account**  
之後他便出現了登入的畫面了  
[<img class="alignnone size-full wp-image-2785" alt="TFS Service Login Screen" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SuccessfullyLogoutfromTFS.png?resize=625%2C406" width="625" height="406" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SuccessfullyLogoutfromTFS.png)  
我便可以登入到正確的**Account**

Hope you find it useful