---
id: 444
title: 'Visual Studio Takes long time to load project &#8212; 在Visual Studio 需要用很多時間來開啟Project'
date: 2010-08-22T00:00:07+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=444
permalink: '/2010/08/visual-studio-takes-long-time-to-load-project-%e5%9c%a8visual-studio-%e9%9c%80%e8%a6%81%e7%94%a8%e5%be%88%e5%a4%9a%e6%99%82%e9%96%93%e4%be%86%e9%96%8b%e5%95%9fproject/'
jabber_published:
  - "1282406863"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1282464711";}";'
tagazine-media:
  - 's:192:"a:7:{s:7:"primary";s:0:"";s:6:"images";a:0:{}s:6:"videos";a:0:{}s:11:"image_count";s:1:"0";s:6:"author";s:8:"15700447";s:7:"blog_id";s:8:"15180134";s:9:"mod_stamp";s:19:"2010-08-20 12:50:43";}";'
categories:
  - .Net Tips And Tricks
  - Microsoft
---
最近朋友說為何開啟**Visual Studio Project** 時會很慢,  
之後發現了原來是因而Visual Studio 在每次開啟Project 時都會嘗試  
把**Visual Studio** 的開發環境還原到你上次在關閉這個Project 之前  
所以如果你上次開啟了很多檔案 [特別是 **ASPX**, 或**WIN FORM**]  
在關閉**Visual Studio** 之前你又忘了關閉這些檔案  
當你再次開啟這個Project 時便需要等一段較長的時間

像我這些在開發時喜歡打開很多檔案但又喜歡只按 關閉 Visual Studio 按鈕來離開Project 的人..  
這會令我覺得比較麻煩..  
所以我在**Microsoft Connect** 中 的**Visual Studio Section**  
發了一個Feedback, 希望將來有一個功能給我們設定在開啟**Project** 時  
可以不打開上次沒有關掉的檔案  
如果大家都覺得有用的話  
請到這個URL 投票支持這個Suggestion  
<a href="https://connect.microsoft.com/VisualStudio/feedback/details/584268/in-vs2010-features-to-allow-user-to-choose-not-to-open-any-unclosed-document-when-open-a-project" target="_blank">in VS2010 Features to allow user to choose not to open any unclosed document when Open a project </a>  
<https://connect.microsoft.com/VisualStudio/feedback/details/584268/in-vs2010-features-to-allow-user-to-choose-not-to-open-any-unclosed-document-when-open-a-project>

謝謝大家