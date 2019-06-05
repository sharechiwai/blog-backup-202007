---
id: 2471
title: This package (or one of its dependencies) contains an init.ps1 file and needs to be installed from the Package Manager Console.
date: 2012-05-11T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2471
permalink: /2012/05/this-package-or-one-of-its-dependencies-contains-an-init-ps1-file-and-needs-to-be-installed-from-the-package-manager-console/
categories:
  - NuGet
tags:
  - Entity Framework 筆記
---
當我嘗試使用**NuGet**來更新**EntityFramework**的**Reference** 時出現了以下的錯誤信息&#8230;  
&#8220;<span style="color: #ff0000;"><strong>This package (or one of its dependencies) contains an init.ps1 file and needs to be installed from the Package Manager Console.</strong></span>&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/9553625495a8406c850b1f91bf346134" alt="This package (or one of its dependencies) contains an init.ps1 file and needs to be installed from the Package Manager Console." width="743" height="457" /> 

說要使用**Package Manager Console** 才可以進行安裝..  
由於我對**NuGet**不知熟識&#8230;  
所以便要花一些時候來做**Research** 看看怎樣使用**NuGet**的 **Package Manager Console**.

**解決方法**:  
原來**Package Manager Console** 應該是在**Visual Studio** 左下方的分頁上的

如果找不到的話可以用以下的方法開啟  
&#8220;**Tools**&#8221; ->&#8221;**Library Package Manager**&#8221; -> 選擇 &#8220;**Package Manager Console**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2ab679a8b29640f1bd8d2ccd8cba4c75" alt="" width="650" height="297" /> 

開啟之後可以在**Console**上輸入以下指令來安裝**Entity Framework**的更新  
**Install-Package EntityFramework**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/588caee37f5c470c8ff9e54da194dda9" alt="Install-Package EntityFramework" width="672" height="173" />  
Update Entity Framework Completed

<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/84aba1e3cfab4752861841beb08311f5" alt="NuGet Update Entity Framework Completed" width="1079" height="249" />  
Hope you find it useful