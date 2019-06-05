---
id: 7
title: 'How to improve ASP.NET Website performance Tips and Tricks &#8212; 如何令你的ASP.NET Website運作得更有效率/走得更快'
date: 2010-08-13T12:27:30+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=7
permalink: '/2010/08/how-to-improve-asp-net-website-performance-tips-and-tricks-%e5%a6%82%e4%bd%95%e4%bb%a4%e4%bd%a0%e7%9a%84asp-net-website%e9%81%8b%e4%bd%9c%e5%be%97%e6%9b%b4%e6%9c%89%e6%95%88%e7%8e%87%e8%b5%b0/'
jabber_published:
  - "1281702450"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1282677963";}";'
categories:
  - ASP.Net Tips and Tricks
---
最近在工作上被人分派了去幫朋友手, 去提升公司其中一個ASP.NET Web Project 的效能&#8230;  
因為這個 Web Portal 比起之前的VERSION 會有更多功能會更好的使用者體驗  
將會在大概一個月後會發報出來給客戶使用&#8230;希望藉些可以吸引更多新客戶/或減小客戶流失&#8230;  
但現在還有一些 效能/速度問題/和使用者體驗方面 需要下一些功夫&#8230;  
你可以想像一下, 即使一個網站有多美&#8230;有多功能&#8230;  
但速度/User Experience反應&#8230;就會令個Web Site 失分..

所以我希望在將來的日子和大家分享一些我在ASP.NET Developement 的經驗  
一些小Tips 這可能會令到你的asp.net 網頁效能更好

以下是小小的 tips, 當我有時間的時候會寫多一些文章加以解釋  
怎樣實踐和為什麼這想做會快一點等等

令到一個ASP.NET Website 慢的原因有很多 [其實 PHP/JSP/其他的 Web 技術]

**1) 使用AJAX**  
如果情況可以的話 用多一些AJAX 的技術..可以減小 全頁更新所需要的的 時間

**2) 設定 EnableViewState=&#8221;False&#8221;**  
在ASP.NET 如果你在 BROWSER 上看看 網頁的原始碼  
你會看到很多字串像

<pre>&lt;input type="hidden" name="__VIEWSTATE" id="__VIEWSTATE"
         value="/wEPDwUKMjA0NzE2Mzc0MmRkl+AVk6NWOQ5A8i+R2UgeVfq0XMY=" /&gt;
</pre>

其實他是ASP.NET 產生出來的 用來記著 網頁的狀態, 很多的 ASP.NET 控制都會產生 ViewState 的  
如果在 ASP.NET Control 上 設定 EnableViewState=&#8221;False&#8221; 便可以減小 這是不知名字串的產生了  
亦都可以加快 頁面 Loading 的速度&#8230; 因為 原始檔會細一點

**3) 使用Paging**  
當在當面上要顯示資料的話, 如果你把這個資料做分頁, 這便可以更加,頁面顯示的Loading 速度

**4) 設定 Caching**  
可以減小 IIS server 的負荷, 可以在一次 不會變的

**5) 優化SQL Query**  
如果你的ASP.NET 網面有用到資料庫的話&#8230;  
如果能夠好好 優化SQL的查詢, 網面的 等候時間也會減小

以上是小弟的 概念&#8230;如果有什麼說得不對..請大家留言更正我的錯誤觀念

Hope you find it useful

待續&#8230;