---
id: 2645
title: Microsoft SQL Server 2012 SP1 Download / Install
date: 2013-03-06T00:00:52+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2645
permalink: /2013/03/microsoft-sql-server-2012-sp1-download-install/
categories:
  - TFS 2012 Sharepoint 2013 Integration
tags:
  - SQL Server 2012
---
當**SQL Server 2012** 安裝完成  
我便想自行安裝 **SQL Server 2012 的Service Pack 1**  
所以便到了**Microsoft Download Center** 下載了  
<a title="Download SQL Server 2012 SP1 ISO" href="http://www.microsoft.com/en-gb/download/details.aspx?id=35575" target="_blank">http://www.microsoft.com/en-gb/download/details.aspx?id=35575</a>  
裡面有多個檔案給我們下載  
[<img class="alignnone size-full wp-image-2646" alt="SQl Server 2012 SP1 Download" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SQL2012SP1DownloadPage.jpg?resize=625%2C529" width="625" height="529" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SQL2012SP1DownloadPage.jpg)

我通常都會直接**Download 64bit**檔案比較大的那個ISO檔  
**E.G.**  
<a title="SQLServer2012SP1-FullSlipstream-ENU-x64.iso" href="http://download.microsoft.com/download/3/B/D/3BD9DD65-D3E3-43C3-BB50-0ED850A82AD5/SQLServer2012SP1-FullSlipstream-ENU-x64.iso" target="_blank">SQLServer2012SP1-FullSlipstream-ENU-x64.iso</a>

以有多好過小的心態來Download  
以確保安裝時候在程式不會下載更多其他檔案&#8230;

誰不知下載完成後安裝時才發現  
剛Download的檔案是一個Full Version的SQL 2012 已經Package了 Service Pack 1 在內  
主要是給新安**裝SQL Server** 或安裝新 **SQL Server Instanc**e 的用戶的&#8230;  
而已安**SQL Server 2012**的用戶..便需要Download  
<a title="SQLServer2012SP1-KB2674319-x64-ENU.exe" href="http://download.microsoft.com/download/3/B/D/3BD9DD65-D3E3-43C3-BB50-0ED850A82AD5/SQLServer2012SP1-KB2674319-x64-ENU.exe" target="_blank">SQLServer2012SP1-KB2674319-x64-ENU.exe</a>

發現以**SQLServer2012SP1-FullSlipstream-ENU-x64.iso** 不能更新SP1後便回到**Download Center**  
發現以下的註解:  
[<img class="alignnone size-full wp-image-2647" alt="SQL Server 2012 SP1 Overview" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SQL2012_Overview.jpg?resize=625%2C307" width="625" height="307" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/04/SQL2012_Overview.jpg)

> Microsoft SQL Server 2012 SP1 Update &#8211; this package contains the Microsoft SQL Server 2012 Service Pack 1 update to be applied to existing SQL Server 2012 installations.
> 
> Microsoft SQL Server 2012 SP1 Slipstream- This package provides the capability to perform new SQL Server 2012 instance installations (or SQL Server 2008/SQL Server 2008 R2 Upgrades) culminating with Service Pack 1 pre-installed. The slipstream installation package consists of a compressed self-extracting .exe and a ‘.box’ payload file that contains the original SQL Server 2012 release along with Service Pack 1. The .exe file can be directly executed, or utilized from the command prompt just as SQL Server 2012 Setup.exe would be (See Install SQL Server 2012 from the Command Prompt).

**中文版:**  
Microsoft SQL Server 2012 SP1 更新：此封裝包含可套用至現有 SQL Server 2012 安裝的 Microsoft SQL Server 2012 Service Pack 1 更新。

> Microsoft SQL Server 2012 SP1 匯集：此封裝提供了一個功能，可以執行全新、預先安裝累積的 SQL Server 2012 執行個體安裝 (或 SQL Server 2008/SQL Server 2008 R2 升級)。此匯集安裝封裝包含自我解壓縮 .exe 和 ‘.box’ 裝載檔案，後者包含原始 SQL Server 2012 版本以及 Service Pack 1。.exe 檔案可以直接執行，或是透過命令提示字元使用，就像 SQL Server 2012 Setup.exe (請參閱從命令提示字元安裝 SQL Server 2012)。

下次要小心一點..不用浪費時間下載用不著的檔案了

Hope you find it useful