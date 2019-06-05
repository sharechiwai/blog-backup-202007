---
id: 587
title: 'ASP.Net Call Javascript Method to make you ASP.Net Application more efficient &#8212; 在ASP.Net 中使  用/呼叫Javascript 令到你的ASP.Net 網站走快一點順一點'
date: 2010-09-07T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=587
permalink: '/2010/09/asp-net-call-javascript-method-to-make-you-asp-net-application-more-efficient-%e5%9c%a8asp-net-%e4%b8%ad%e4%bd%bf-%e7%94%a8%e5%91%bc%e5%8f%abjavascript-%e4%bb%a4%e5%88%b0%e4%bd%a0%e7%9a%84asp-ne/'
jabber_published:
  - "1283790921"
email_notification:
  - "1283790922"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1283982587";}";'
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
  - Javascript
---
最近因為要幫朋友改善他的**ASP.Net Project** 所以記下了一些使用**ASP.Net 的心得**&#8230;  
希望可以增加**User Experience**的  
大家有時間可以參考一下&#8230;

如果大家覺得有用的話..請留言給我&#8230;  
這會給我有更加多的動力去寫多一些想這像的網誌 =)  
可以改善我寫網誌的技巧

在ASP.Net 提供了一個十分方便的開發環境給我們  
其中ASP.Net 提供了ASP.Net Ajax Control ToolKits  
令到我們可以不用寫任何的Javascript 便可以實現用Javascript 的效果

但是他們都是**Server Side Control**..  
所以需要進行**PostBack**, 把資料/**Request**傳到**Server**上  
之後**Server** 再把網頁/部分網頁**Render**到我們的Browser 中  
這或多或小都會令到 顯示網頁有小小的Delay的&#8230;  
令到使用者體驗不太好

如果可以在**ASP.Net** 中使用一些**Javascript** 這便事半功倍了 =)  
今天想會大家介紹如何在**ASP.Net** 中 使用**Javascript**

在ASP.Net 中我們不可像在**Windows Application** 一樣  
使用**MessageBox.Show** 來顯然 信息

但是我們可以運用**ASP.Net Code Behind** 來使用/呼叫**Javascript**功能  
在沒有**Update Panel** 的情況下我們可以使用以下的程式碼實行 在**ASP.Net call Javascript method**

**VB.Net**  
<span style="color:#008000;">Page.ClientScript.RegisterStartupScript(Me.GetType, &#8220;ShareChiWaiJS&#8221;, &#8220;alert(&#8216;Welcome to ShareChiWai&#8217;);&#8221;, True)</span>

**C#**  
<span style="color:#008000;">Page.ClientScript.RegisterStartupScript(this.GetType(), &#8220;ShareChiWaiJS&#8221;, &#8220;alert(&#8216;Welcome to ShareChiWai&#8217;); &#8220;, true);</span>

**解釋**  
<span style="color:#008000;">Page.ClientScript.RegisterStartupScript(&#8220;這個類 System.Tye&#8221;, &#8220;Key Name&#8221;, &#8220;你將會使用到的 Javascript;&#8221;, &#8220;加上Script Tag E.g. 自動加上 <script type=&#8217;text/javascript&#8217;> </script>&#8221;)</span>

現在相信大家都可以在**ASP.Net** 中使用/呼叫**Javascript** 了  
Hope you find it useful

待續&#8230; 下集  
[Call Javascript in ASP.Net UpdatePanel —在ASP.Net 的 UpdatePanel 中使用/呼叫Javascript](http://sharechiwai.wordpress.com/2010/09/08/call-javascript-in-asp-net-updatepanel-%E5%9C%A8asp-net-%E7%9A%84-updatepanel-%E4%B8%AD%E4%BD%BF%E7%94%A8%E5%91%BC%E5%8F%ABjavascript/)