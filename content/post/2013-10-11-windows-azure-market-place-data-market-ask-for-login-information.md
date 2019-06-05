---
id: 2971
title: Windows Azure Market Place Data market ask for login information
date: 2013-10-11T00:00:23+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2971
permalink: /2013/10/windows-azure-market-place-data-market-ask-for-login-information/
categories:
  - Windows Azure
tags:
  - Data Market
  - Windows Azure
---
很久之前便用過**Windows Azure** 的 **Data Service**  
不知道什麼時候他升級了變成 **Windows Azure Data market**

<a title="Windows Azure Data Market" href="http://datamarket.azure.com/" target="_blank">http://datamarket.azure.com/</a>

今天在電腦活動上要嘗試使用**Windows Azure Data Market** 上的 資料時  
瀏覽器彈出了一個要求輸入使用者名稱和密碼的pop-up  
[<img class="alignnone size-full wp-image-2972" alt="DataMarket Azure Ask for Username Password" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/DataMarket-Azure-Ask-for-Username-Password.jpg?resize=456%2C324" width="456" height="324" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/DataMarket-Azure-Ask-for-Username-Password.jpg)  
但是我已經使用了我的**Windows Live Account** / **Microsoft Account**  
當我再次嘗試轉入我的登入資料後還是不能登入  
&#8220;<span style="color: #ff0000;"><strong>The authorization type you provided is not supported. Only Basic and OAuth are supported</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2973" alt="The authorization type you provided is not supported. Only Basic and OAuth are supported" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/The-authorization-type-you-provided-is-not-supported.-Only-Basic-and-OAuth-are-supported.jpg?resize=625%2C101" width="625" height="101" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/The-authorization-type-you-provided-is-not-supported.-Only-Basic-and-OAuth-are-supported.jpg)

做了一會**Research** 之後..  
發現..原來我要轉入的是 **Account Keys**  
**Username 是 Account Keys 內的 Description**  
**Password 是 Account Keys 入的 Value**  
大家可以到 在網頁上的 &#8220;**My Account**&#8221; -> &#8220;**Account Keys**&#8221; 上找到你的**Account Key**資訊

[<img class="alignnone size-full wp-image-2974" alt="Account Keys  Windows Azure Marketplace Account Key" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/Account-Keys-Windows-Azure-Marketplace-Account-Key.jpg?resize=625%2C274" width="625" height="274" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/Account-Keys-Windows-Azure-Marketplace-Account-Key.jpg)

或者到以下網扯  
<a title="Windows Azure Data Market Account Keys" href="https://datamarket.azure.com/account/keys" target="_blank">https://datamarket.azure.com/account/keys</a>

之後便可以在**Login Popup** 上輸入這些資料了  
其實這些登入資料主要是用來給大家在程式上連接到這個 **DataMarket** 時作認證的  
所以不要像我一樣以為用**Windows Live Account** / **Microsoft Account** 便可以登入 =P

Hope you find it useful