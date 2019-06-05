---
id: 501
title: 'VB.Net Convert String To Date&#8221;ddd MMM d HH:mm:ss zz00 yyyy&#8221; &#8212;- VB.Net日期時間轉換的問題  &#8220;ddd MMM d HH:mm:ss zz00 yyyy&#8221;'
date: 2010-08-26T00:00:14+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=501
permalink: '/2010/08/vb-net-convert-string-to-dateddd-mmm-d-hhmmss-zz00-yyyy-vb-net%e6%97%a5%e6%9c%9f%e6%99%82%e9%96%93%e8%bd%89%e6%8f%9b%e7%9a%84%e5%95%8f%e9%a1%8c-ddd-mmm-d-hhmmss-zz00-yyyy/'
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1282846140";}";'
jabber_published:
  - "1282772117"
categories:
  - .Net Tips And Tricks
---
今日在網上看到了一個 關於日期時間轉換的問題  
這個日期的文字表示是這樣的 &#8220;Fri Aug 27 20:10:08 +0800 2010&#8221;  
格式應該是 &#8220;**ddd MMM d HH:mm:ss zz00 yyyy**&#8220;,

如果我們直接把這個 <span style="color: #008000;">String </span>轉換成<span style="color: #008000;">DateTime </span>E.G.

[vb]  
Dim dString as string = "Fri Aug 27 20:10:08 +0800 2010"  
MsgBox(Convert.ToDateTime(dString))  
[/vb]

我們便會遇到這樣的Error 錯誤  
**<span style="color: #ff0000;">FormatException was unhandled<br /> String was not recognized as a valid DateTime.</span>**  
[<img class="alignnone size-full wp-image-502" title="FormatException" src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8c12e8e2091543d4a860190ba914a530" alt="" />](http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8c12e8e2091543d4a860190ba914a530)

&nbsp;

所以我們便要動動腦筋&#8230;看看怎麼才能把 <span style="color: #0000ff;">&#8220;Fri Aug 27 20:10:08 +0800 2010&#8221;</span> 轉成<span style="color: #0000ff;">DateTime </span>了

[vb]  
Dim cInfo As System.Globalization.CultureInfo  
cInfo = System.Globalization.CultureInfo.CreateSpecificCulture("en-gb") &#8216; 不同Locale/ Culture 都有不同的 DateFormat 的格式

Dim DateFormat As String = "ddd MMM d HH:mm:ss zz00 yyyy"  
MsgBox(DateTime.Now.ToString(DateFormat, cInfo)) &#8216;用這段Code 可以用來看看 把現在的時間轉做上面的格式  
Dim d As DateTime = DateTime.ParseExact(dString, DateFormat, cInfo) &#8216; 這段CODE Convert String to Date  
MsgBox(d) &#8216;當然要看看 能不能做到想要的效果  
[/vb]

Hope you find it useful