---
id: 3949
title: The target principal name is incorrect. Cannot generate SSPI context
date: 2017-03-26T00:00:33+08:00
author: ShareChiWai
layout: post
categories:
  - .Net Tips And Tricks
tags:
  - Connection String
---

由於最近公司有 Product go Live, 所以有很多時候有些 urgent 的問題要解決

又不幸的。。。我的電腦剛剛安裝好。。還安裝了**Visual Studio 2017**.
當我嘗試執行公司的 Project 時。。出現了以下的錯誤信息。。
"<span style="color: #ff0000;"><strong>The target principal name is incorrect. Cannot generate SSPI context</strong></span>"
<img class="alignnone size-full wp-image-3954" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/connectionstring.png?resize=625%2C213" alt="The target principal name is incorrect. Cannot generate SSPI context" width="625" height="213" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />

起初還以為是**Visual Studio**或**SQL Server**版本問題。。
當我仔細看了這個 Error message 和 **connection string** 之後。。
便發現問題是來自 Connection string" 因為有了兩隻不同的**Login**方法
而我們的**電腦在 Server 上沒有 Login 的 Permission**

原本的**connection string**

```<add name="ShareChiWaiContext" providerName="System.Data.SqlClient" connectionString="Data Source=sharechiwai.com;Initial Catalog=Blog;User ID=testUser;Password=TestPassword;Integrated Security=True;MultipleActiveResultSets=True" />

```

只要**移除**了 **integrated = true** 便可以了
解決了的 Connection String
E.g

```<add name="ShareChiWaiContext" providerName="System.Data.SqlClient" connectionString="Data Source=sharechiwai.com;Initial Catalog=Blog;User ID=testUser;Password=TestPassword;MultipleActiveResultSets=True" />

```

Hope you find it useful
