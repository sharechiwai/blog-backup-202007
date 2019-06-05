---
id: 2310
title: My JQuery Cheat Sheet 1
date: 2012-04-03T00:00:14+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2310
permalink: /2012/04/my-jquery-cheat-sheet-1/
categories:
  - Jquery Notes
tags:
  - Cheatsheet
---
今天去了一個**Hack Day**&#8230;  
發現..原來自己很小記下 自己寫過的程式碼..  
除了一些日常用的 程式碼外..  
多數都是複製之前做過的..之後加以修改便可以解決問題&#8230;  
[我真的不是一個好的Programmer&#8230;]  
所以今天決定好好為自己寫下一些有關**JQuery**或Javascript的 Cheatsheet..  
把所有暫時覺得十分有用..實用的 JQuery程式碼/功能都 放在這一個網誌上..  
方便將來找功能時使用 =P..

**以下是我的小小Cheatsheet**

我們可以用以下的Code 去連接我們的**JQuery Library**  
如果可以的話..最好是使用**CDN** (**Content Delivery Network**)上的copy  
因為這樣子可以縮短延遲時間&#8230;因為**CDN** 把一些靜態的檔案散佈在不同地區的**Server**上&#8230;所以用戶**Browser** 能夠自動的選擇最近的檔案Download, 縮短延遲時間  
另一個原因是可以減輕你的**Server**上的負荷 &#8211; 因為可以分流了到**CDN**, 和些多Browser都會有一些限制..不允許在同一時間向同一個website/hostname 開啟很多的連接. 當你使用了**CDN** 的話&#8230;其中一個檔案的連接便會是向這個CDN 的網址 request/請求的  
令這個Browser可以繼續request你網頁上其他的資源/檔案

**CDN** 亦都以提供更好的緩存..如果其他website也有用同一個**CDN**的話..當用戶的Browser看到 之前已經有其他Request到CDN上同一個檔案時..Browser會自動Caches了這一個檔案[應該是最多一年的時間]&#8230;待將來有同一個檔案的Request時 Browser 也不需要再次download這個檔案  
這可以減低**Brandwidth** 和增加page load的速度

[javascript]  
<html>  
<head>  
<title> ShareChiWai </title>

<script type="text/javascript" src="http://ajax.microsoft.com/ajax/jquery/jquery-1.7.2.min.js"></script>  
<script type="text/javascript">  
if (typeof jQuery == &#8216;undefined&#8217;)  
{

alert(unescape("%3Cscript src=&#8217;/js/jquery-1.7.2.min.js&#8217; type=&#8217;text/javascript&#8217;%3E%3C/script%3E"));

}  
</script>

</head>

<body>

</body>  
</html>  
[/javascript]

下一次將會介紹一些 簡單又實用的功能

Hope you find it useful