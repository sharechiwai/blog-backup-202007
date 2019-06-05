---
id: 538
title: 'VB.Net Open PDF/ or Launch a program or Batch File &#8212; VB.Net 如何打開PDF 檔 或.Bat 其他程式'
date: 2010-09-01T00:00:16+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=538
permalink: '/2010/09/vb-net-open-pdf-or-launch-a-program-or-batch-file-vb-net-%e5%a6%82%e4%bd%95%e6%89%93%e9%96%8bpdf-%e6%aa%94-%e6%88%96-bat-%e5%85%b6%e4%bb%96%e7%a8%8b%e5%bc%8f/'
jabber_published:
  - "1283271441"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1283982580";}";'
categories:
  - .Net Tips And Tricks
---
有朋友問如何可以在VB.Net 開啟PDF/ Excel XLS 檔案, 因為在我們的應用程式需要 看看使用者想把資料Export 到 Excel/PDF 後打開檔案給使用者看

其實解決方法十分簡單  
我們可以用System.Diagnostics.Process來實行這個工作  
<span style="color:#008000;"><strong>System.Diagnostics.Process.Start(&#8220;pdf的檔案FULL PATH 和 FILENAME&#8221;)</strong></span>

E.G.  
**開啟PDF 檔**  
**<span style="color:#008000;">System.Diagnostics.Process.Start(&#8220;F:LearningShareChiWai.pdf&#8221;)</span>**

**開啟網頁**  
**<span style="color:#008000;">System.Diagnostics.Process.Start(&#8220;http://sharechiwai.wordpress.com/&#8221;)</span>**

Hope your find it useful