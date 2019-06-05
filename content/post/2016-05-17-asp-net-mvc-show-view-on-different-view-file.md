---
id: 3674
title: ASP.Net MVC Show View on Different View File
date: 2016-05-17T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3674
permalink: /2016/05/asp-net-mvc-show-view-on-different-view-file/
categories:
  - ASP.Net MVC
tags:
  - ASP.Net
  - ASP.Net MVC
---
給自己一個小小的A**SP.Net MVC** 筆記  
就是如何在**ASP.Net MVC** 上的 **Action** Load不同的 **View 檔案**  
通常在**ASP.Net MVC** 的**Default Action**的**View**通常會存在  
<span style="color: #008000;"><strong>View</strong></span>/<span style="color: #3366ff;"><strong>ControllerName的資料夾內的</strong></span>/<span style="color: #ff0000;">Action同名的.cshtml檔案</span>  
但是有時候我們可能有數個不同的**Action**但是顯示的view 可能是一樣的

**解決方法**十分簡單  
我們只需要在 **return View**的時候**加入那個.cshtml的檔案名[不包含 file extension]**

E.g.

<pre>return View("Index")
</pre>

hope you find it useful