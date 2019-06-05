---
id: 2790
title: 'HTML5 check if Browser support LocalStorage &#8211; HTML5 檢查 瀏覽器是否支援ＬocalStorage'
date: 2013-04-21T00:00:42+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2790
permalink: '/2013/04/html5-check-if-browser-support-localstorage-html5-%e6%aa%a2%e6%9f%a5-%e7%80%8f%e8%a6%bd%e5%99%a8%e6%98%af%e5%90%a6%e6%94%af%e6%8f%b4%ef%bd%8cocalstorage/'
categories:
  - HTML/CSS
tags:
  - HTML5
  - LocalStorage
---
雖然現在有很多&#8221;**瀏覽器**/**Browser**&#8221; 都支援 **HTML5**..  
但是別要忘記..雖然科技和工具都在..  
但是用戶未必會把現有的 **&#8220;瀏覽器**/**Browser**&#8221; 更新到最近的版本..  
所以有時候我們也都要 當在網頁 Load的時候檢查一下.. 用戶的 **&#8220;瀏覽器**/**Browser**&#8221; 支不支援 **LocalStorage**.. [如果你的**WebSite**有用這個技術的話]  
之後便可以作出對應的方法..  
令到使用者體驗更好

**解決方法**:  
我們可以使用**Javascript** 來檢查 一下 &#8220;**Storage**&#8221; 這一個Object 是不是 &#8220;<span style="color: #ff0000;"><strong>undefined</strong></span>&#8221; 的..  
如果是的話 那你的&#8221;**瀏覽器**/**Browser**&#8221; 便不支援 **Local Storage** 了

**E.G.**

[javascript]  
<script>  
//Check if browser support Local Storage  
if(<strong>typeof(Storage) =="undefined"</strong>)  
{  
alert("LocalStorage does not support on your browser..\n Please upgrade you browser in order to run this application");  
}  
</script>  
[/javascript]

Hope you find it useful