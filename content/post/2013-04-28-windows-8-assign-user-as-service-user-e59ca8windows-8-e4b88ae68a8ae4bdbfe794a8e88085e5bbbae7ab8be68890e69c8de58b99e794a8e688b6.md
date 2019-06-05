---
id: 2812
title: 'Windows 8 Assign User as Service User &#8211; 在Windows 8 上把使用者建立成服務用戶'
date: 2013-04-28T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2812
permalink: '/2013/04/windows-8-assign-user-as-service-user-%e5%9c%a8windows-8-%e4%b8%8a%e6%8a%8a%e4%bd%bf%e7%94%a8%e8%80%85%e5%bb%ba%e7%ab%8b%e6%88%90%e6%9c%8d%e5%8b%99%e7%94%a8%e6%88%b6/'
categories:
  - Windows 8
tags:
  - Group Policy
  - Local Security Policy
---
上一次介紹了在**Windows 8**上建立一個 &#8220;**Local User** / **本機使用者**&#8221;

#### <a title="Permalink to Windows 8 Create Local User/ Local Account  – 在Windows 8上建立本機用戶/本機使用者" href="http://blog.sharechiwai.com/2013/04/windows-8-create-local-user-local-account-%e5%9c%a8windows-8%e4%b8%8a%e5%bb%ba%e7%ab%8b%e6%9c%ac%e6%a9%9f%e7%94%a8%e6%88%b6%e6%9c%ac%e6%a9%9f%e4%bd%bf%e7%94%a8%e8%80%85/" rel="bookmark">Windows 8 Create Local User/ Local Account – 在Windows 8上建立本機用戶/本機使用者</a>

之後..由於程式上的需要把使用者建立成**Service User** &#8220;**User as Service User**&#8221;  
[<img class="alignnone size-full wp-image-2817" alt="RedGate SQL Backup - User has been granted the Log On as A service right" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/RedGateSQLBackup5.png?resize=625%2C164" width="625" height="164" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/RedGateSQLBackup5.png)  
主要是用來執行**Database Backup** 的

如何在**Windows 8** 上 **Create User as Service User**呢?

解決方法十分簡單..  
我們可以通過本機上的 &#8220;**Local Security Policy**&#8221; 來設定的

**解決方法**:  
開啟 &#8220;**控制台** / **Control Panel**&#8221; -> &#8220;**管理員工具** / **Administrative Tools**&#8221;  
開啟 &#8220;**Local Security Policy**&#8221;  
[<img class="alignnone size-full wp-image-2813" alt="Control Panel - Administrative Tools" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/LocalSecurityPolicy.png?resize=625%2C238" width="625" height="238" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/LocalSecurityPolicy.png)

在&#8221;**Local Security Policy**&#8220;視窗 上  
開啟 &#8220;**Security Settings**&#8221; -> &#8220;**Local Policies**&#8221; -> &#8220;**User Rights Assignment**&#8221;  
[<img class="alignnone size-full wp-image-2814" alt="Local Security Policy - Log on as service user" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/LogOnAsServiceGroup.png?resize=625%2C447" width="625" height="447" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/LogOnAsServiceGroup.png)

在右手面的視窗 上 會看到 &#8220;**Log on as a service**&#8221; 的 選項  
開啟&#8221;**Log on as a service**&#8221; 選項  
之後按下 &#8220;**Add User or Group**&#8221; 輸入需要加到 &#8220;**Log on as a service**&#8221; 的用戶名稱 後按 &#8220;**確定** / **OK**&#8221;  
[<img class="alignnone size-full wp-image-2815" alt="Add User To Log In As Service Group - Log in as service" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/AddUserToLogInAsServiceGroup.png?resize=625%2C408" width="625" height="408" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/AddUserToLogInAsServiceGroup.png)  
便可以了

Hope you find it useful