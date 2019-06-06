---
id: 4011
title: ASP.Net Core Enable Development Error
date: 2017-07-01T12:07:06+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=4011
permalink: /2017/07/asp-net-core-enable-development-error/
categories:
  - .net core
tags:
  - dotnet
  - dotnet core
  - dotnet tips and tricks
---
由於不太了解 **ASP.Net Core with Angular / React Webpack** 的關係  
當遇到有 **Angular** / **React**的問題是都不知道那裡出錯  
* 我的**Angular** / **ReactJs** Project是用 **dotnet core 的 SPA template** 建立的

過了幾天才發現..  
由於是使用

<pre>dotnet run
</pre>

或

<pre>dotnet watch run
</pre>

的關係  
所以執行的 port 和visual studio執行時debug 的port不一樣..  
可能是這樣所以被定義為不是 **development mode**  
所以網頁的error 便被隱藏了

**解決方法**有兩個

**解決方法 1**  
我們可以在**Startup.cs**  
**Enable Developer Error** 便可以了  
E.G.  
在以下的function 上

<pre>public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
      
</pre>

移除這個If statement  
當程式遇到錯誤時執行這個Developer Error

<pre>/*
if (env.IsDevelopment())
            {
                app.UseDeveloperExceptionPage();
                app.UseWebpackDevMiddleware(new WebpackDevMiddlewareOptions {
                    HotModuleReplacement = true
                });
            }
            else
            {
                app.UseExceptionHandler("/Home/Error");
            }
*/

 app.UseDeveloperExceptionPage();
                app.UseWebpackDevMiddleware(new WebpackDevMiddlewareOptions {
                    HotModuleReplacement = true
                });
</pre>

** [<img class="alignnone size-large wp-image-4013" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/startupcs.png?resize=625%2C287" alt="startup.cs" width="625" height="287" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/startupcs.png?resize=1024%2C470 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/startupcs.png?resize=300%2C138 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/startupcs.png?resize=768%2C352 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/startupcs.png?resize=624%2C286 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/startupcs.png?w=1510 1510w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/startupcs.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/startupcs.png)  
解決方法 2**  
這個方法比理性  
就是更改 開發電腦的 **Environment Variable Settings**  
我們可以使用**Command prompt**  
執行以下指令設定**環境變數** **Environment Variable**

<pre>set ASPNETCORE_ENVIRONMENT=Development
</pre>

**[<img class="alignnone size-large wp-image-4012" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/aspnetCoreEvvironment.png?resize=625%2C105" alt="Set up ASPNETCORE Environment Variable" width="625" height="105" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/aspnetCoreEvvironment.png?resize=1024%2C172 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/aspnetCoreEvvironment.png?resize=300%2C50 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/aspnetCoreEvvironment.png?resize=768%2C129 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/aspnetCoreEvvironment.png?resize=624%2C105 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/aspnetCoreEvvironment.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/07/aspnetCoreEvvironment.png)**  
詳情可以參考以下網頁  
<https://docs.microsoft.com/en-us/aspnet/core/fundamentals/environments>

Hope you find it useful