---
id: 3993
title: ASP.net Core SPA Single Page Application Template Generator with angular, aurelia, knockout, react
date: 2017-06-20T06:51:03+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3993
permalink: /2017/06/asp-net-core-spa-single-page-application-template-generator-with-angular-aurelia-knockout-react/
categories:
  - .net core
tags:
  - dotnet
  - dotnet core
  - SPA
---
最近開始學 **Angular 4** / **React**  
但是不知道怎樣開始  
如果只是**React** / **Angular** 的 CLI 來產生他們的 **Project Template** 的話 自己便要再起一個**Node JS** 的backend 來serve data 了

**安裝方法**:  
我們可以在Command prompt 執行以下指令

<pre>dotnet new --install Microsoft.AspNetCore.SpaTemplates::*
</pre>

之後便可以執行以下指令 去看看有什麼 **Template** 可以使用

<pre>dotnet new
</pre>

[<img class="alignnone size-large wp-image-3994" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/dotnetnew.png?resize=625%2C347" alt="dotnet new" width="625" height="347" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/dotnetnew.png?resize=1024%2C568 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/dotnetnew.png?resize=300%2C167 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/dotnetnew.png?resize=768%2C426 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/dotnetnew.png?resize=624%2C346 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/dotnetnew.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/dotnetnew.png)  
建立一個新資料夾之後進入這資料夾執行  
以下指令到 建立你的 **angular SPA site with Dotnet core backend**

<pre>dotnet new angular
</pre>

完成後可以執行以下指令到run 這個project

<pre>dotnet restore 
npm install
dotnet run
</pre>

hope you find it useful