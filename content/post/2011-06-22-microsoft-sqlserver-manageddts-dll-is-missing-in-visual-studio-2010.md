---
id: 1822
title: Microsoft.SQLServer.ManagedDTS.dll is Missing in Visual Studio 2010
date: 2011-06-22T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1822
permalink: /2011/06/microsoft-sqlserver-manageddts-dll-is-missing-in-visual-studio-2010/
categories:
  - .Net Tips And Tricks
tags:
  - MSSQL
---
今天希望為我之前寫的程式加入執行**SQL Server Integrated Services [SSIS] Package**的功能..  
其實我之前在**Codeplex** 上發報的<a title="ShareChiWai SSIS WCF Services" href="http://ssisservices.codeplex.com/" target="_blank">ShareChiWai SSIS WCF Services</a>已經學習過怎樣可以在程式上執行**SSIS Package**…  
所以我便嘗試複製/貼上在<a title="ShareChiWai SSIS WCF Services" href="http://ssisservices.codeplex.com/" target="_blank">ShareChiWai SSIS WCF Services</a> 上執行**SSIS Package**的程式碼到 要升級的Project上..  
由於我們要加入”**Microsoft.SQLServer.ManagedDTS.dll**” 這個DLL 才可以有  
namespaces 來執行**SSIS Package**..如果沒有加入這個**參考/reference**的話..  
你便會得到以下錯誤信息..  
<a href="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/74a8032a1c154ecd919abcc7ebcf257b/renditions/fullsize.jpg" target="_blank"><img title="Missing Namespaces" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/74a8032a1c154ecd919abcc7ebcf257b/renditions/fullsize.jpg?resize=625%2C148" alt="" width="625" height="148" data-recalc-dims="1" /><br /> </a>“**Namespace or type specified in the Imports ‘Microsoft.SqlServer.Dts.Runtime’ doesn’t contain any public member or cannot be found. Make sure the namespace or the type is defined and contains at least one public member. Make sure the imported element name doesn’t use any aliases.**”  
<a href="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/80e0c9396206417599e71fd902e2e3f8/renditions/fullsize.jpg" target="_blank"><img title="Missing Namespaces" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/80e0c9396206417599e71fd902e2e3f8/renditions/fullsize.jpg?resize=437%2C124" alt="" width="437" height="124" data-recalc-dims="1" /></a>

但是我忘了那裡可以找到**Microsoft.SQLServer.ManagedDTS.dll** 這個DLL..  
最後終於找到了…  
如果大家有差不多的問題..希望這個Post可以幫到你  
解決放法:  
只要你在加入**參考/Add Reference** 視窗 上選擇”**Browse tab/瀏覽 分頁**”  
之後在地址列上 貼上 “**C:\Windows\assembly\GAC_MSIL\Microsoft.SQLServer.ManagedDTS**” 按開啟..之後你應該可以找到 “**Microsoft.SQLServer.ManagedDTS.dll**” 的  
<a href="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f81c15691447438f8cf20c3adff982a4/renditions/fullsize.jpg" target="_blank"><img title="\Microsoft.SQLServer.ManagedDTS Path" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f81c15691447438f8cf20c3adff982a4/renditions/fullsize.jpg?resize=625%2C266" alt="" width="625" height="266" data-recalc-dims="1" /></a>  
在我的電腦上還有一個資料來”10.0.0.0__xxxxxxx”

<a href="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/24dda19b3f7744c4bb692e0c06122ef2/renditions/fullsize.jpg" target="_blank"><img title="Microsoft.SQLServer.ManagedDTS" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/24dda19b3f7744c4bb692e0c06122ef2/renditions/fullsize.jpg?resize=563%2C412" alt="" width="563" height="412" data-recalc-dims="1" /></a>  
Hope you find it useful

&nbsp;