---
id: 2280
title: '.Net 取得ClickOnce  Publish 發布的 Version Number'
date: 2012-01-05T00:00:46+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2280
permalink: '/2012/01/net-%e5%8f%96%e5%be%97clickonce-publish-%e7%99%bc%e5%b8%83%e7%9a%84-version-number/'
categories:
  - .Net Tips And Tricks
---
今天為了方便同事知道他們在使用中的程式是那一個版本..  
我決定了在程式上的**Status Bar**上 顯示出**Application**的 **Deployment Version Number**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/528b51a9ffe04268a7d8d594e788917f" alt="publish version number" width="856" height="539" />  
解決方法十分簡單:

**解決方法**:  
我們可以使用以下的程式碼取得**Version Number**的資料

**VB**

[vb]  
MessageBoxShow(ApplicationDeployment.CurrentDeployment.CurrentVersion.ToString)  
[/vb]

**C Sharp**

[csharp]  
MessageBoxShow(ApplicationDeployment.CurrentDeployment.CurrentVersion.ToString);  
[/csharp]

我的程式的Example  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/efd9e485fa1642d98d27035c304b2523" alt="screen shot of showing version number" width="233" height="100" />  
Hope you find it useful