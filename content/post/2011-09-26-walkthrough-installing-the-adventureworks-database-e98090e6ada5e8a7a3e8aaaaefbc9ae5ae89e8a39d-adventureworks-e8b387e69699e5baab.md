---
id: 2103
title: 'Walkthrough: Installing the AdventureWorks Database  &#8211; 逐步解說：安裝 AdventureWorks 資料庫'
date: 2011-09-26T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2103
permalink: '/2011/09/walkthrough-installing-the-adventureworks-database-%e9%80%90%e6%ad%a5%e8%a7%a3%e8%aa%aa%ef%bc%9a%e5%ae%89%e8%a3%9d-adventureworks-%e8%b3%87%e6%96%99%e5%ba%ab/'
categories:
  - .Net Tips And Tricks
  - MSSQL Tips and Tricks
---
今天應承了朋友寫一篇**demo** 是關於 **Download Microsoft SQL Server 2005** 的樣本數據庫**Adventureworks** 的安裝程序的

記得很久之前也嘗試過安裝**Adventureworks**的 數據庫..由於我不知喜歡使安裝東西的關係..我以我用了別的方法把這個**Sample Database** 加到我的數據庫上

今天的**Sample** 是用了**Microsoft SQL Server 2005 的樣本數據庫Adventureworks**  
大家可以到**Codeplex**處下載  
 <http://msftdbprodsamples.codeplex.com/releases/view/4004>

會建議大家使用**Recommeded Download**的這一個 **AdventureWorksDB.msi**  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/5a2e506a7e4b473b9ba287f92b4aa53b/renditions/fullsize.jpg?resize=625%2C412" alt="download AdventureWorksDB.msi" width="625" height="412" data-recalc-dims="1" />  
按一下連結之後便會出現一個 **License**的**Agreement**的東西  
按一下&#8221;**I Agree**&#8221; 來繼續下載這個**Sample Database**

之後記下這個**Sample Database** 下載到的位置  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/06f558cd7a864041af4fab3d39e2d104/renditions/fullsize.jpg?resize=625%2C440" alt="Download AdventureWorksDB to specific Folder" width="625" height="440" data-recalc-dims="1" />  
下載完成後 大家便會看到電腦上多了一個&#8221;**AdventureWorksDB.msi**&#8221;

如果大家有解壓縮的程式的話..  
可以在&#8221;**AdventureWorksDB.msi**&#8221; 按一下滑鼠右鍵 之後選擇 你有的解壓縮程式  
[我的是 &#8220;**7-zip**&#8220;] ->之後把這個**檔案解壓縮到&#8221;AdventureWorksDB&#8221;資料夾上** [**Extract To &#8220;AdventureWorksDB\**&#8220;]  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e32c32885483480296e5918897246dbe/renditions/fullsize.jpg?resize=625%2C431" alt="Unzip AdventureWorksDB.msi" width="625" height="431" data-recalc-dims="1" />  
之後打開 &#8220;**AdventureWorksDB**&#8221; 資料夾 便會看到有2個檔案  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/22629ae97836431188c1505a1b41c91a/renditions/fullsize.jpg?resize=573%2C194" alt="AdventureWorksDB Folder" width="573" height="194" data-recalc-dims="1" />  
**adventureworks_data.mdf** &#8212; AdventureWorks 的 數據  
**adventureworks_log.mdf** &#8212; AdventureWorks的日誌

之後我們便可以把這2個檔案複製到我們的數據庫的資料夾上&#8230;  
方便 附加到數據庫上

數據庫資料夾的位置大概在這裡  
[我的是**SQL Server 2008 Express Edition**]  
<span style="color: #3366ff;"><strong>C:\Program Files\Microsoft SQL Server\MSSQL10.SQLEXPRESS\MSSQL\DATA</strong></span>

如果你的**SQL Server** 沒有更改位何位置的話  
應該是可以到以下 **Directory** 看到你電腦上有安裝的**SQL Server**的資料夾的  
<span style="color: #3366ff;"><strong>C:\Program Files\Microsoft SQL Server\</strong></span>  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/719c7c4c66194776b7c8081884b7d5ee/renditions/fullsize.jpg?resize=625%2C279" alt="SQL Server Folder" width="625" height="279" data-recalc-dims="1" /> 

<span style="color: #3366ff;"><strong>C:\Program Files\Microsoft SQL Server\MSSQL10_50.MSSQLSERVER\</strong></span>

把這2個檔案複製到我們的數據庫的資料夾後使可以開啟我們的**SQL Server Management Studio** 把數據庫 **Attach** 到我們的**Server** 上了

打開&#8221;**SQL Server Management Studio**&#8221;  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/48be7b1ccd024f449a74d79591958818/renditions/fullsize.jpg?resize=414%2C418" alt="Launch SQL Server Management Stufio" width="414" height="418" data-recalc-dims="1" />  
由於我的電腦上有2個**SQL Database 的Server**..而今次的實驗是以**SQL Server 2008 Express Edition**來做試驗的關係  
所以在**Server Name**上使用了 &#8220;**(local)\SQLExpress**&#8221;  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/9888adf1df744c87b28a3c9927b1a16f/renditions/fullsize.jpg?resize=448%2C331" alt="SQL Server Management Studio SQL Express Connection String" width="448" height="331" data-recalc-dims="1" />  
輸入好登入資料後按連接

之後在**Management Studio** 上打開數據庫資料夾..我們只可以看見有一個資料夾&#8221;**System Database**&#8221;  
這說明了我的**SQL Server**上是沒有數據庫的  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d8dffa0a6b66446eb903dcbde4ed5b36/renditions/fullsize.jpg?resize=448%2C312" alt="Empty Database Server" width="448" height="312" data-recalc-dims="1" />  
之後我們可以在&#8221;**Database**&#8220;資料夾上按滑鼠右鍵 之後選擇 &#8220;**Attach&#8230;**&#8221;  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0e4b145b5e3c46acb7e0f8ac11f0e3e4/renditions/fullsize.jpg?resize=377%2C333" alt="Database Folder Right Click and select 'Attach...'" width="377" height="333" data-recalc-dims="1" />  
在&#8221;**Attach Database**&#8221; 視窗中按一下&#8221;**Add&#8230;/增加&#8230;**&#8221;  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/dc19c8906ca040649f20ce1a7525817e/renditions/fullsize.jpg?resize=625%2C562" alt="Attach Database" width="625" height="562" data-recalc-dims="1" />  
之後在**MSSQL** 的**Data** 資料夾上 選擇&#8221;**adventureworks_data.mdf**&#8221; 後按&#8221;**OK/確定**&#8221;  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8571531e307742c7bdf00f0661bfa34b/renditions/fullsize.jpg?resize=625%2C564" alt="Attach Database Select Adventureworks_data.mdf" width="625" height="564" data-recalc-dims="1" /> 

之後有可能會問你 &#8220;<span style="color: #ff0000;"><strong>If you are certain that you have added all the necessary full-text catalogs, click OK. To Add more catalogs, click Cancel</strong></span>&#8221;  
按&#8221;**OK**&#8221;  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/5e3e875e56294e31b651e51a2bfde121/renditions/fullsize.jpg?resize=625%2C566" alt="If you are certain that you have added all the necessary full-text catalogs, click OK. To Add more catalogs, click Cancel" width="625" height="566" data-recalc-dims="1" />  
在&#8221;**Attach Database**&#8220;視窗上按&#8221;**OK**&#8221; 之後**SQL Server**便會**Attach** 這個**AdventureWorksDB 到數據庫**了  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/33165e05adde417fab1619d6240944e9/renditions/fullsize.jpg?resize=625%2C561" alt="Attach Database Dialog" width="625" height="561" data-recalc-dims="1" /> 

**Attaching Database &#8211; 附加數據庫中**  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/98dbc377e2074ae9a2752ed8186da7c6/renditions/fullsize.jpg?resize=625%2C557" alt="attaching Datbase" width="625" height="557" data-recalc-dims="1" />  
之後大家便可以看到在&#8221;**Database**&#8221; 資料夾內多了一個數據庫.叫**AdventureWorks**了  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f113b3ff903d4fabb17b324e662c5750/renditions/fullsize.jpg?resize=625%2C497" alt="Attached Adventure Work Database" width="625" height="497" data-recalc-dims="1" />  
大功告成..大家可以開始練習T-SQL 了

Hope you find it useful