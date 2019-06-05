---
id: 1824
title: Unable to open module file .NET Framework,Version=v4.0.AssemblyAttributes.vb
date: 2011-05-30T00:00:07+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1824
permalink: /2011/05/unable-to-open-module-file-net-frameworkversionv4-0-assemblyattributes-vb/
categories:
  - .Net Tips And Tricks
---
今天打開**Visual Studio 2010** 嘗試**compile/debug**寫之前的程式時  
出現了以下 錯誤信息

“**Unable to open module file ‘C:\Users\Chi\AppData\Local\Temp**  
**\.NETFramework,Version=v4.0.AssemblyAttributes.vb’: System Error &H80070002&**”  
<a href="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e56619fbd36f47a3a8e389b95946814a/renditions/fullsize.jpg" target="_blank"><img title="Unable to open module file  NET Framework,Version=v4.0.AssemblyAttributes.vb" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e56619fbd36f47a3a8e389b95946814a/renditions/fullsize.jpg?resize=625%2C138" alt="" width="625" height="138" data-recalc-dims="1" /></a>  
之後嘗試**Clean Solution**/**Clean Project**和 **Rebuild Solution**/**Rebuild Project**  
也沒有解決到這個錯誤

最後終於找到了解決方法..

**解決方法**  
就是重新啟動**Visual Studio 2010**便可

Hope you find it useful

&nbsp;