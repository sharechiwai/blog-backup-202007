---
id: 2919
title: 'VS2010 connnect to tfs2012 crash/hang &#8211; Visual Studio 2010 連接到 TFS Server 2012 當機問題'
date: 2013-09-22T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2919
permalink: '/2013/09/vs2010-connnect-to-tfs2012-crashhang-visual-studio-2010-%e9%80%a3%e6%8e%a5%e5%88%b0-tfs-server-2012-%e7%95%b6%e6%a9%9f%e5%95%8f%e9%a1%8c/'
categories:
  - TFS 2012 Sharepoint 2013 Integration
---
把公司**的TFS2010** 升級到**TFS 2012 with SharePoint 2013 Integration** 之後  
有一個同事當他在**Visual Studio 2010 Check-out TFS Project或 Check-In 他的程式碼時**  
出現**Hang** / **當機**的情況&#8230;

這個情況在我和另一個同事的電腦上都沒有問題  
很可惜這個同事不太理性&#8230;只懂投訴是新的**TFS** 的問題  
而不去嘗試找解決的方法..

我之前都建議他做**Windows Update**..  
可惜都不能解決..

由於他太煩了.所以我最後安裝了一部**Virtual Machine**入面有**Visual Studio 2010**的  
叫他**Remote Desktop** 到這台電腦嘗試工作..看看有沒有出現同樣問題..  
結果..這台電腦是沒有問題的.

這樣我們便可以確定這是他的電腦問題..而不是TFS 2012的問題了

**解決方法**: [但是不是100% ]  
今天當他再次嘗試做**Windows Update**的時候  
發現原來**Visual Studio 2010 有Feature Pack 2** 的

當他下載及安裝後.暫時都沒有出現Hang機/當機的情況了

如果大家有**crash**/**hang** 的問題..  
我會建議大家嘗試做**Windows Update**以確保電腦和**Visual Studio**有最新的更新

有時間大家可以參考一下 以下網址  
有關**Visual Studio 和 TFS Server兼容性的資訊**

**Compatibility between Team Foundation Clients and Team Foundation Server**  
<a title="Compatibility between Team Foundation Clients and Team Foundation Server" href="http://msdn.microsoft.com/en-us/library/vstudio/dd997788.aspx" target="_blank">http://msdn.microsoft.com/en-us/library/vstudio/dd997788.aspx</a>

**Visual Studio 2010 SP1 Team Foundation Server 2012 Compatibility GDR**  
<a title="Visual Studio 2010 SP1 Team Foundation Server 2012 Compatibility GDR" href="http://www.microsoft.com/en-gb/download/details.aspx?id=29082" target="_blank">http://www.microsoft.com/en-gb/download/details.aspx?id=29082</a>

<span style="color: #ff0000;"><strong>2013-10-02 更新</strong></span>

同事還久不久有連接**TFS 2012**時Hang 機的情況  
但清除 自己電腦上的**TFS Caches Folder** 之後好像便解決了  
**解決方法**:

可以嘗試到以下 資料夾  
&#8220;**%UserProfile%\AppData\Local\Microsoft\Team Foundation**&#8221;  
[<img alt="Start -> Run -> TFS Cache Folder" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/UserProfileTFSCacheFolder.jpg?resize=430%2C217" width="430" height="217" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/UserProfileTFSCacheFolder.jpg)  
清除上面所有的資料夾的檔案  
以清除你電腦上的**TFS** 的**Caches  
[<img alt="Team Foundation Cache Folder" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/Team-Foundation-Cache-Folder.jpg?resize=586%2C172" width="586" height="172" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/Team-Foundation-Cache-Folder.jpg)**  
Hope you find it useful