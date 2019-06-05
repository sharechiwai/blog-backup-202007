---
id: 2955
title: Visual Studio 2008 Connect to TFS 2012 Issue
date: 2013-10-08T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2955
permalink: /2013/10/visual-studio-2008-connect-to-tfs-2012-issue/
categories:
  - TFS 2012 Sharepoint 2013 Integration
---
今天我另一位同事又投訴當他的嘗試使用 **Visual Studio 2008** 連接到**TFS2012** 時出現了Timeout 的情況

幸好之前在**Visual Studio 2010** 時遇過差不多的情況  
所以都大概知道有什麼方法可以解決

## <a href="http://blog.sharechiwai.com/2013/09/vs2010-connnect-to-tfs2012-crashhang-visual-studio-2010-%e9%80%a3%e6%8e%a5%e5%88%b0-tfs-server-2012-%e7%95%b6%e6%a9%9f%e5%95%8f%e9%a1%8c/" rel="bookmark">VS2010 connnect to tfs2012 crash/hang – Visual Studio 2010 連接到 TFS Server 2012 當機問題</a>

**解決方法**:  
大家可以到以下網址下載及安裝  
<a title="Visual Studio 2008 SP1 Compatibility GDR for Visual Studio 2012 Team Foundation Server and Team Foundation Service Preview" href="http://www.microsoft.com/en-gb/download/details.aspx?id=29983" target="_blank">Visual Studio 2008 SP1 Compatibility GDR for Visual Studio 2012 Team Foundation Server and Team Foundation Service Preview</a>

這應該可以解決**TFS2012 和 VS2008 的相容性問題**

如果問題還是出現的話  
可以嘗試到以下 資料夾  
&#8220;<span style="color: #0000ff;"><strong>%UserProfile%\AppData\Local\Microsoft\Team Foundation</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2956" alt="Start -> Run -> TFS Cache Folder" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/UserProfileTFSCacheFolder.jpg?resize=430%2C217" width="430" height="217" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/UserProfileTFSCacheFolder.jpg)  
清除上面所有的資料夾的檔案  
以清除你電腦上的**TFS** 的**Caches  
[<img class="alignnone size-full wp-image-2957" alt="Team Foundation Cache Folder" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/Team-Foundation-Cache-Folder.jpg?resize=586%2C172" width="586" height="172" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/Team-Foundation-Cache-Folder.jpg)  
** 

Hope you find it useful