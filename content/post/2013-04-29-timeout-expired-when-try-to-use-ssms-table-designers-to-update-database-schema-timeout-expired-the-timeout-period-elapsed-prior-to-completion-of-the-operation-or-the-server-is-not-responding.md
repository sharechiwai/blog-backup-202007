---
id: 2820
title: 'Timeout expired &#8211; when try to use SSMS Table Designers to update Database Schema &#8211; Timeout expired.  The timeout period elapsed prior to completion of the operation or the server is not responding.'
date: 2013-04-29T00:00:57+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2820
permalink: /2013/04/timeout-expired-when-try-to-use-ssms-table-designers-to-update-database-schema-timeout-expired-the-timeout-period-elapsed-prior-to-completion-of-the-operation-or-the-server-is-not-responding/
categories:
  - MSSQL Tips and Tricks
---
今天當我儲存已修改的公司一個資料庫 &#8220;**表單** / **Table** &#8220;的**Schema** 時  
出現了以下的一個錯誤..令到我不能把這個修改儲存..  
&#8220;<span style="color: #ff0000;"><strong>Timeout expired. The timeout period elapsed prior to completion of the operation or the server is not responding.</strong></span>&#8221;  
錯誤信息是這樣的  
[<img class="alignnone size-full wp-image-2821" alt="Post Save Notifications Timeout" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/PostSaveNotificationsTimeout.jpg?resize=580%2C458" width="580" height="458" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/PostSaveNotificationsTimeout.jpg)

&#8220;&#8216;**<span style="color: #ff0000;">ShareChiWai_Demo&#8217; table</span>**  
** <span style="color: #ff0000;">&#8211; Unable to modify table.</span>**  
** <span style="color: #ff0000;">Timeout expired. The timeout period elapsed prior to completion of the operation or the server is not responding.</span>**&#8221;

**解決方法**:  
我們只需要更改我個的 **SQL Server Management Studio** [**SSMS**] 的選擇便可以解決這個問題  
在**SSMS** 上按一下 &#8220;**工具** / **Tool**&#8221; 列 &#8230; 之後按一下 &#8220;**選項&#8230;** / **Options&#8230;**&#8221;  
[<img class="alignnone size-full wp-image-2822" alt="SQL2012 Tools -> Options" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQL2012ToolsOptions.png?resize=625%2C259" width="625" height="259" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQL2012ToolsOptions.png)

在 &#8220;**選項&#8230;** / **Options&#8230;**&#8220;的視窗上的左手邊 選擇 &#8220;**Designer** / **設計**&#8221;  
在右手邊的屬性內容 在 &#8220;**Transaction time-out after:** &#8221; 的屬性上修改 **timeout**的時間為更大的數值便可以了  
[<img class="alignnone size-full wp-image-2823" alt="SQL2012 Tools -> Options -> Designer Settings" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQL2012ToolsOptionsDesignerSettings.png?resize=625%2C421" width="625" height="421" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/06/SQL2012ToolsOptionsDesignerSettings.png)  
完成後 按&#8221;**確定** / **OK**&#8221;

之後便可以儲存了 &#8230; 大家可以再次嘗試一下

Hope you find it useful