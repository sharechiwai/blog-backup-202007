---
id: 2921
title: 'The path is already mapped in workspace MachineName;username &#8211; Remove/Delete workspace on TFS'
date: 2013-10-01T00:00:44+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2921
permalink: /2013/10/the-path-is-already-mapped-in-workspace-machinenameusername-removedelete-workspace-on-tfs/
categories:
  - TFS 2012 Sharepoint 2013 Integration
tags:
  - TFS
---
今天在建立一個新的project時出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>The path is already mapped in workspace MachineName;username</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2923" alt="TFS - The path is already mapped in workspace MachineName;username" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/Mapped.png?resize=414%2C103" width="414" height="103" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/Mapped.png)

<span style="color: #ff0000;"><strong>Workspace already exist iss</strong><strong>u</strong>e</span>, 這個問題..令我苦惱了數天

可能是因為在同一部電腦上用了不同的**TFS Account**  
和另外一部電腦上的電腦名稱在這部電腦一樣  
當我嘗試在**Mapping Folder**時出現以下的錯誤信息

令我不能**Check-in** 我的**Source Code**  
我亦都不能**Map to Local**  
所以即使我更新了我的程式碼也不知道可以怎麼辦&#8230;

做了一會兒research 之後.終於找到了解決方法了  
如果知道這一個**Workspace**是不會再用的話 你便可以使用**Visual Studio 的 Command Line Tools** 來刪除你某一個**TFS Account** 的**Workspace**

**解決方法:**  
我們需要使用&#8221;**Visual Studio 2012**&#8221; 中的 &#8220;**Developer Command Prompt for VS2012**&#8221;  
[<img class="alignnone size-full wp-image-2922" alt="Visual Studio 2012 - Developer Command Prompt for VS2012" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/VS2012DeveloperCmd.png?resize=423%2C224" width="423" height="224" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/VS2012DeveloperCmd.png)  
或者其他的**Visual Studio** 的 **Command Prompt**也可以  
開啟了&#8221;**Developer Command Prompt for VS2012**&#8221;  
輸入 以下指令來刪除 **TFS Server** 上的 **Workspace**

>**tf workspace /delete /server:**[<span style="color: #339966;"><strong>Server Name/ Server URL 和Collection名</strong></span>];<span style="color: #339966;"><strong>[workspace的使用者名稱 (這個應該和你之前所得到的錯誤信息的是一樣的)</strong></span>]  
之後按&#8221;**Enter**/**輸入**&#8221;  
他便會向你出示警告信息..說一旦 **Workspace**被刪除便不能復原  
如果你確認要刪除**Workspace**的話 輸入 &#8220;**Yes**&#8221; 否則 輸入 &#8220;**No**&#8221;  
[<img class="alignnone size-full wp-image-2924" alt="TFS Delete Workspace via Command Prompt" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/DeleteWOrkSpace.png?resize=625%2C137" width="625" height="137" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/DeleteWOrkSpace.png)

輸入&#8221;**Yes**&#8220;之後按下&#8221;**Enter** / **輸入**&#8220;後你的**Workspace**便會;被刪除..  
[<img class="alignnone size-full wp-image-2925" alt="TFS Delete Workspace via Command Prompt [Completed]" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/DeleteWOrkSpaceCompleted.png?resize=625%2C175" width="625" height="175" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/DeleteWOrkSpaceCompleted.png)

之後當你再次**Check-in**或**Map folder to local** 時應該不會出現之前的錯誤信息的

Hope you find it useful