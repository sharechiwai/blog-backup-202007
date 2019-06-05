---
id: 3012
title: 'VS2013 &#8211; An error occurred. Detailed message: An error was raised by libgit2. Category = Net (Error). This transport isn&#8217;t implemented. Sorry (Fixed)'
date: 2014-02-12T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3012
permalink: /2014/02/vs2013-an-error-occurred-detailed-message-an-error-was-raised-by-libgit2-category-net-error-this-transport-isnt-implemented-sorry-fixed/
categories:
  - Visual Studio
tags:
  - BitBucket
  - Git
  - troubleshooting
  - Visual Studio 2013
---
今天嘗試使用 把程式碼 **Commit** 到**Bitbucket** 上  
之前介紹的**AppHarbor** 可以把你在**BitBucket**上的 Source Code Compile 和Deploy 到你的**AppHarbor Account** 上  
十分方便..

### <a href="http://blog.sharechiwai.com/2014/01/appharbor-free-hosting-for-asp-net-asp-net-mvc-%e5%85%8d%e8%b2%bbasp-net-asp-net-mvc%e5%af%84%e5%ad%98%e6%9c%8d%e5%8b%99/" rel="bookmark">AppHarbor – Free hosting for ASP.Net/ ASP.Net MVC – 免費ASP.Net/ ASP.Net MVC寄存服務</a>

我先在**BitBucket** 建立一個 **C#** 的**Project**/**repository**

之後使用**Tortoise for Git**來把在**BitBucket** 的**Repository Clone** / **複製**到電腦上

<img class="alignnone" alt="Get BitBucket SSH URL to clone the project repository" src="https://i2.wp.com/farm8.staticflickr.com/7314/12478579685_0b58a863be_z.jpg?resize=385%2C201" width="385" height="201" data-recalc-dims="1" /> 

之後便用**Visual Studio 2013** 建立一個新的**Project** 儲存在 那個資料夾上..

當大家再次開啟這個**Project**的時候便會發現 在檔案上 Right Click / 按右鍵時 會多了一個 &#8220;**Commit**&#8220;的選項

<div style="width: 650px" class="wp-caption alignnone">
  <img alt="" src="https://i2.wp.com/farm8.staticflickr.com/7314/12479218165_761e79017b_z.jpg?resize=625%2C606" width="625" height="606" data-recalc-dims="1" />
  
  <p class="wp-caption-text">
    Commit option on visual studio
  </p>
</div>

如果大家有連接到**TFS** 的專案時..會有 &#8220;**Check-in**&#8221; 的選項的..

之後便會去到 以下的這個畫面.. 大家可以 **Commit** 和把已經 **commit** 的 **Source Code Push** 到 **remote Repository**上

<img class="alignnone" alt="Commit and Push Visual Studio 2013" src="https://i0.wp.com/farm6.staticflickr.com/5482/12479702564_b59082c3d1_z.jpg?resize=370%2C236" width="370" height="236" data-recalc-dims="1" /> 

誰不知.. 當我按 &#8220;**Push**&#8221; 這個按鈕後便出現以下的錯誤信息..

&#8220;<span style="color: #ff0000;"><strong>An error occurred. Detailed message: An error was raised by libgit2. Category = Net (Error).</strong></span>  
<span style="color: #ff0000;"><strong> This transport isn&#8217;t implemented. Sorry</strong></span>&#8221;  
<img class="alignnone" alt="An error occurred. Detailed message: An error was raised by libgit2.  Category = Net (Error). This transport isn't implemented. Sorry" src="https://i2.wp.com/farm6.staticflickr.com/5479/12479712724_2156226bac_z.jpg?resize=469%2C469" width="469" height="469" data-recalc-dims="1" /> 

做了一會兒research 之後發原來**Visual Studio 2012** 使用**Git**時也有相同的問題  
可惜可以在**Visual Studio 2012**上使用的**Visual Studio Extension**不能**在Visual Studio 2013**上使用

如果你是使用**Visual Studio 2012** 的話..  
可以嘗試下載和 安裝 **Visual Studio Tools for Git**  
<a title="Visual Studio Tools for Git" href="http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c" target="_blank">http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c</a>

如果你是使用**Visual Studio 2013** 的話 可以嘗試以下的方法

解決方法..原來**Visual Studio 2013** 是支援用**HTTPS** 來 連絡 到**GIT** 的  
通常很多人都會使用**SSH**&#8230;

所以大家可以到你的 **BitBucket** / **GIT**/ **CodePlex** 上的 **GIT Repository**  
之後選擇以 **HTTPS**的方法來 **Clone** / **複製**你的 **Repository** 到你的電腦上  
<img class="alignnone" alt="BitBucket HTTPS option" src="https://i1.wp.com/farm8.staticflickr.com/7455/12487712485_f293db22d6_d.jpg?resize=353%2C195" width="353" height="195" data-recalc-dims="1" />  
<img class="alignnone" alt="Git Repository by using HTTPS" src="https://i1.wp.com/farm8.staticflickr.com/7292/12479702534_691c5de48c_z.jpg?resize=521%2C410" width="521" height="410" data-recalc-dims="1" /> 

當你再次開啟Visual Studio 2013 按 &#8220;Push&#8221; / &#8220;Pull&#8221; 或 &#8220;Sync&#8221; 的話  
Visual Studio 應該會彈出一個登入的windows 讓你轉入 BitBucket / GIT/ CodePlex  
的Username / Password [請注意..你的 Password 可能和你SSH 的Passphrase 是不同的&#8230;所以可能會輸入錯的密碼]

BitBucket request for login information  
<img class="alignnone" alt="BitBucket Request for User Credentials inside Visual Studio 2013" src="https://i0.wp.com/farm4.staticflickr.com/3803/12479371523_1f14c23d6f_z.jpg?resize=522%2C489" width="522" height="489" data-recalc-dims="1" /> 

成功登入後**Visual Studio**便會 &#8220;**Push**&#8221; / &#8220;**Pull**&#8221; 或 &#8220;**Sync**&#8221; 到 **BitBucket** / **GIT**/ **CodePlex** /**TFS** 上了  
&#8220;**Repository is already up to date. No changes to pull**&#8221;  
<img class="alignnone" alt="Repository is already up to date. No changes to pull" src="https://i0.wp.com/farm6.staticflickr.com/5537/12479217825_5d02b069c5_z.jpg?resize=368%2C310" width="368" height="310" data-recalc-dims="1" /> 

現在便可以在**Visual Studio 2013** 上使用 **Git** 來 Commit &#8220;**Push**&#8221; / &#8220;**Pull**&#8221; 或 &#8220;**Sync**&#8221; 你的 **Source code** 到 **BitBucket** / **GIT**/ **CodePlex** /**TFS** 上了

Happy Coding