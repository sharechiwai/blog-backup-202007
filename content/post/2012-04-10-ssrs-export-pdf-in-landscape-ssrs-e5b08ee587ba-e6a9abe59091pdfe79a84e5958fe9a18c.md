---
id: 2322
title: 'SSRS Export PDF in Landscape &#8211; SSRS 導出 橫向PDF的問題'
date: 2012-04-10T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2322
permalink: '/2012/04/ssrs-export-pdf-in-landscape-ssrs-%e5%b0%8e%e5%87%ba-%e6%a9%ab%e5%90%91pdf%e7%9a%84%e5%95%8f%e9%a1%8c/'
categories:
  - SQL Server Reporting Services
tags:
  - SSRS
---
最近公司開始使用**SSRS** (**SQL Server Reporting Services**)..因為他是**SQL Server** 其中一個功能..  
之前使用的**Crystal Report 11 R2** 都比較舊..  
和**Syntax**上和**SQL**有點不同..看起來比較複雜  
新同事都不希望開時間學習  
所以現在所有新的**Report**都是用 **SSRS** 寫的  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c3976642dd004103a8bd099fc03a2bd7" alt="Share ChiWai SSRS Sample" width="1011" height="605" />  
今天終於發現了一個問題&#8230;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e84a05e031794320aacabca2a736c0f5" alt="SSRS Default Page orientation" width="1017" height="776" />  
雖然在&#8221;Page Layout&#8221;上的&#8221;**Page Setup**&#8221; ->&#8221;**Orientation**&#8220;選擇了&#8221;**Landscape**/**橫向**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c777c611967f44d8b921c1e117310a46" alt="SSRS Change Print Layout Page setup to Landscape" width="1026" height="787" /> 

在**Design mode**的時候也是顯示為&#8221;**Landscape**/**橫向**&#8220;的  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/59b40eb6f6394b279644637462f51a0f" alt="SSRS Page preview after changing Print Layout to Landscape" width="1015" height="780" /> 

在**Preview mode**的時候也以&#8221;**Landscape**/**橫向**&#8220;顯示  
之後我便嘗試**Export**這個**Report** 為**PDF**了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e97dcb26dfb340e59c7d22b4f15ebf0a" alt="SSRS Export PDF" width="935" height="533" />  
但是**Export**了出來的Report卻是&#8221;**Portrait** /**直向**&#8220;的&#8230;

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/9e58f1e666fe434bb70b447d3e6b11d7" alt="SSRS Export PDF Portrait after change Print Layout" width="585" height="804" /> 

做了一會兒research之後終於找到解決方法了

**解決方法**:  
只要在**Report**的&#8221;**Properties**/**內容**&#8220;上 改變**page size** 的**properites** 便可以了  
在**Report**上空白的地方按&#8221;**Mouse Right Click**&#8221;  
之後選擇&#8221;**Report Properties**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/c3bf779ba22e4eafbcfd55c44aeafcba" alt="SSRS Report Properties" width="1017" height="783" /> 

大家可以在&#8221;**Report Properties**&#8221; 上的&#8221;**Page Setup**&#8221; ->之後在&#8221;**Page Units**&#8220;上 選擇&#8221;**Landscape**/**橫向**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/46ddf1084a6d4153902e3747821075cb" alt="SSRS Report Properties -> Page Setup ->Landscape" width="683" height="527" /> 

再一次**Export**的時候.. 便是 &#8220;**Landscape/橫向**&#8220;了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f8fabdc808c144b5a435b955eaa92da1" alt="Export PDF in Landscape format " width="582" height="799" /> 

Hope you find it useful