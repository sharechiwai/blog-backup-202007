---
id: 609
title: .Net File.Create The Process cannot access the file because it is being used by another process. File.Create 該進程無法訪問文件 因為它正由另一個進程使用
date: 2010-09-09T05:00:28+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=609
permalink: '/2010/09/net-file-create-the-process-cannot-access-the-file-because-it-is-being-used-by-another-process-file-create-%e8%a9%b2%e9%80%b2%e7%a8%8b%e7%84%a1%e6%b3%95%e8%a8%aa%e5%95%8f%e6%96%87%e4%bb%b6-%e5%9b%a0/'
jabber_published:
  - "1283981162"
email_notification:
  - "1283981163"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1284381900";}";'
categories:
  - .Net Tips And Tricks
---
當你嘗試使用.Net 中的  **File.Create** 來建立檔案 之後直接把檔案開啟..  
你可能會遇到以下的Error Message  
<span style="color: #ff0000;">The Process cannot access the file because it is being used by another process.</span>  
或  
<span style="color: #ff0000;">該進程無法訪問文件 因為它正由另一個進程使用</span>  
[<img title="msg" src="https://i0.wp.com/farm6.static.flickr.com/5067/5688394582_fdf4269ba0.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5067/5688394582_fdf4269ba0.jpg)  
其實原因是很簡單的  
因為使用**File.Create** 時會建立一個**FileStream** 的Object  
而這個**Stream** 會被你定在運行中的**Application**使用  
直到你把這個**Stream** 關閉  
或你離開這程式時&#8230;這個**Stream** 才會被關閉

如果我們想用程式碼來建立一個空白的檔案  
我們可以使用以下方法  
<span style="color: #008000;">File.Create(&#8220;F:LearningShareChiWai.txt&#8221;).Close()</span>  
&#8216;這會在電腦上建立一個空白檔案. 之後使用,**Close()**來關閉這個**FileStream**  
這裡大家便可以直接把檔案開啟了

如果大家想建立一個文字檔和 把文字寫進 這個文字檔可以參考以下的程式碼  
&#8216;首先我們建立一個  
<span style="color: #008000;">Dim sw As New StreamWriter(&#8220;F:LearningShareChiWai.txt&#8221;)</span>

sw.WriteLine(&#8220;Welcome to Share ChiWai&#8221;)  
&#8216;我們可以使用StreamWriter.WriteLine把文字寫進檔期之後建立一個新行

&#8216;我們可以用sw.Write() 把文字寫進檔案  
&#8216;但他們不會自動建立新行的  
sw.Write(&#8220;Hope &#8220;)  
sw.Write(&#8220;you enjoy &#8220;)  
sw.Write(&#8220;my Blog &#8220;)  
&#8216;可以用sw.WriteLine()來建立一個空行  
sw.WriteLine()  
sw.Write(&#8220;大家多多指教&#8221;)  
&#8216;寫完檔期後當然要把這個Stream 關閉  
sw.Close()

Hope you find it useful