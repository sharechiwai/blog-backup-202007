---
id: 590
title: 'Call Javascript in ASP.Net UpdatePanel &#8212;在ASP.Net 的 UpdatePanel 中使用/呼叫Javascript'
date: 2010-09-08T00:00:56+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=590
permalink: '/2010/09/call-javascript-in-asp-net-updatepanel-%e5%9c%a8asp-net-%e7%9a%84-updatepanel-%e4%b8%ad%e4%bd%bf%e7%94%a8%e5%91%bc%e5%8f%abjavascript/'
jabber_published:
  - "1283875311"
email_notification:
  - "1283875313"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1284381901";}";'
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
  - Javascript
---
在之前的 網誌 [ASP.Net Call Javascript Method to make you ASP.Net Application more efficient — 在ASP.Net 中使用/呼叫Javascript 令到你的ASP.Net 網站走快一點順一點](http://sharechiwai.wordpress.com/2010/09/07/asp-net-call-javascript-method-to-make-you-asp-net-application-more-efficient-%E5%9C%A8asp-net-%E4%B8%AD%E4%BD%BF-%E7%94%A8%E5%91%BC%E5%8F%ABjavascript-%E4%BB%A4%E5%88%B0%E4%BD%A0%E7%9A%84asp-ne/)

介紹了如何使用**ASP.Net Code Behind 來使用/呼叫Javascript**  
令到你的ASP.Net 網站走快一點順一點  
相信大家很多時候都會使用**UpdatePanel** 或**ASP.Net Aja**x 的技術  
但當你的頁面上有UpdatePanel 時便可能用不著這些在之前的網誌所介紹的 Code了&#8230;  
我研究了一段日子..  
最後找到了解決方法 =)

就是使用**ScriptManager.RegisterStartupScript** 來代替 **Page.ClientScript.RegisterStartupScript** 了

**VB.Net**  
<span style="color:#008000;">ScriptManager.RegisterStartupScript(Me, Me.GetType, “ShareChiWaiJS”, “alert(‘Welcome to ShareChiWai’);”, True)</span>

**C#**  
<span style="color:#008000;">ScriptManager.RegisterStartupScript(this, Page.GetType(), ShareChiWaiJS”, “alert(‘Welcome to ShareChiWai’); “, true);</span>

**解釋**  
<span style="color:#008000;">ScriptManager.RegisterStartupScript(&#8220;頁Page&#8221;, &#8220;Type 都是頁&#8221;, “Key Name”, “你將會使用到的 Javascript;”, “加上Script Tag E.g. 自動加上 <script type=’text/javascript’> </script>”);</span>

Hope you find it useful.