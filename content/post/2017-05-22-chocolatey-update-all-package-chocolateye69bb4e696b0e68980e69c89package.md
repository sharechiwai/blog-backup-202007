---
id: 3972
title: Chocolatey Update All Package -Chocolatey更新所有Package
date: 2017-05-22T21:42:59+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3972
permalink: '/2017/05/chocolatey-update-all-package-chocolatey%e6%9b%b4%e6%96%b0%e6%89%80%e6%9c%89package/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Chocolately
  - Package Manager
  - PowerShell
---
之前同事介紹了 如何使用 **Chocolately** 來安裝軟件  
現在發現他和其他**Package Manager** 一樣  
可以使用command 直接更新所有Package 十分好用

**解決方法**  
我們使需要使用管理員權限開啟 **PowerShell**  
之後執行以下 command

<pre>choco upgrade all -y
</pre>

<img class="alignnone size-large wp-image-3974" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/chocoUpgradeAll.png?resize=625%2C458" alt="Chocolatey Update all Package" width="625" height="458" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/chocoUpgradeAll.png?resize=1024%2C751 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/chocoUpgradeAll.png?resize=300%2C220 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/chocoUpgradeAll.png?resize=768%2C563 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/chocoUpgradeAll.png?resize=624%2C458 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/chocoUpgradeAll.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
完成後會說名有那些**package** 已經更新了  
[<img class="alignnone size-large wp-image-3973" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/ChocoUpdatedPackage.png?resize=625%2C458" alt="Chocolatey Update all Package" width="625" height="458" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/ChocoUpdatedPackage.png?resize=1024%2C751 1024w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/ChocoUpdatedPackage.png?resize=300%2C220 300w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/ChocoUpdatedPackage.png?resize=768%2C563 768w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/ChocoUpdatedPackage.png?resize=624%2C458 624w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/ChocoUpdatedPackage.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/05/ChocoUpdatedPackage.png)

Hope you find it useful