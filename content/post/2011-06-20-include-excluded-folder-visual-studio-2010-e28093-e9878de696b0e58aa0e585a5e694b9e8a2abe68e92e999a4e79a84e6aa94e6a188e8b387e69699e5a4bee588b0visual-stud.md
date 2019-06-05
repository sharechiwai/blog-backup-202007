---
id: 1815
title: Include excluded folder Visual Studio 2010 – 重新加入改被排除的檔案/資料夾到Visual Studio 2010
date: 2011-06-20T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1815
permalink: '/2011/06/include-excluded-folder-visual-studio-2010-%e2%80%93-%e9%87%8d%e6%96%b0%e5%8a%a0%e5%85%a5%e6%94%b9%e8%a2%ab%e6%8e%92%e9%99%a4%e7%9a%84%e6%aa%94%e6%a1%88%e8%b3%87%e6%96%99%e5%a4%be%e5%88%b0visual-stud/'
categories:
  - .Net Tips And Tricks
---
今天開始學習 **ASP.Net MVC** 這個技術  
由於我是**ASP.Net MVC** 新手的關係..  
所以腦海裡滿是**Asp.Net**的 concept  
很多地方都不太明白..

今天想建立一個**Model** 來嘗試下..  
我便想在**Model Folder**上按右鍵… “**Add/加入**” -> “**New Item/新增**”  
<a href="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/05c157dc2a3c468b80711e5c1531e43d/renditions/fullsize.jpg" target="_blank"><img title="Add New Item - ASP.Net MVC Model" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/05c157dc2a3c468b80711e5c1531e43d/renditions/fullsize.jpg?resize=625%2C370" alt="" width="625" height="370" data-recalc-dims="1" /></a>  
誰不知我一時手振…按了”**Exclude From Project**”  
<a href="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3aa4c970cdc14bebb18e9f100ac1b875/renditions/fullsize.jpg" target="_blank"><img title="Model Folder Excluded from the Project" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3aa4c970cdc14bebb18e9f100ac1b875/renditions/fullsize.jpg?resize=262%2C286" alt="" width="262" height="286" data-recalc-dims="1" /></a>

之後便不知道怎樣才可以在**Visual Studio 上重新加入改被排除的檔案/資料夾**到了  
嘗試建立一個新的資料夾”**Models**” 卻得到以下的錯誤信息..  
<a href="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/71d3ea1335a6457ba22791817a160abd/renditions/fullsize.jpg" target="_blank"><img title="Folder Already Exist in the project" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/71d3ea1335a6457ba22791817a160abd/renditions/fullsize.jpg?resize=625%2C250" alt="" width="625" height="250" data-recalc-dims="1" /></a>  
最後..我的朋友來解求了我..

**解決方法:**

在**Solutions Explorer** 上有多個Icon  
分別是  
“**Properies**”  
“**Show All Files**”  
“**Refresh**”  
“**ASP.Net Configuraion**”  
<a href="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/dd197515266a49ea817a0e1a3f1b574e/renditions/fullsize.jpg" target="_blank"><img title="Solution Explorer's Icon" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/dd197515266a49ea817a0e1a3f1b574e/renditions/fullsize.jpg?resize=331%2C146" alt="" width="331" height="146" data-recalc-dims="1" /></a>

我們可以按一下 “**Show All Files / 顯示所有檔案**”  
之後便會看到了一些不同顏色的檔案/資料夾..

被**Exclude**了的檔案/資料夾 通常都會變成白色的  
<a href="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/be54e02dbe194533acb978566b8dac9f/renditions/fullsize.jpg" target="_blank"><img title="Show All Files View" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/be54e02dbe194533acb978566b8dac9f/renditions/fullsize.jpg?resize=287%2C183" alt="" width="287" height="183" data-recalc-dims="1" /></a>  
在要被**Include**的檔案/資料夾上按右鍵..  
“**Include In Project/包括在項目**”  
<a href="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7a18e69108e644138b6bc7d1ab71cdfb/renditions/fullsize.jpg" target="_blank"><img title="Include In Project Visual Studio" src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7a18e69108e644138b6bc7d1ab71cdfb/renditions/fullsize.jpg?resize=583%2C352" alt="" width="583" height="352" data-recalc-dims="1" /></a>  
之後你便可以看到這個檔案/資料夾 變回正常顏色了

最後發現..原來**ASP.Net MVC Project**上是沒有**Model Template**的  
所以要自己在**Model Folder**上建主一個**Class** 使可以了

Hope you find it useful

&nbsp;