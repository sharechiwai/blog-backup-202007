---
id: 690
title: 'IE9 Beta Review 5 &#8212; IE9 Beta 使用者心得5'
date: 2010-09-23T00:00:18+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=690
permalink: '/2010/09/ie9-beta-review-5-ie9-beta-%e4%bd%bf%e7%94%a8%e8%80%85%e5%bf%83%e5%be%975/'
jabber_published:
  - "1285171578"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1285243812";}";'
email_notification:
  - "1285171579"
tagazine-media:
  - 's:525:"a:7:{s:7:"primary";s:60:"http://sharechiwai.files.wordpress.com/2010/09/inspector.jpg";s:6:"images";a:1:{s:60:"http://sharechiwai.files.wordpress.com/2010/09/inspector.jpg";a:6:{s:8:"file_url";s:60:"http://sharechiwai.files.wordpress.com/2010/09/inspector.jpg";s:5:"width";s:3:"649";s:6:"height";s:3:"669";s:4:"type";s:5:"image";s:4:"area";s:6:"434181";s:9:"file_path";s:0:"";}}s:6:"videos";a:0:{}s:11:"image_count";s:1:"1";s:6:"author";s:8:"15700447";s:7:"blog_id";s:8:"15180134";s:9:"mod_stamp";s:19:"2010-09-19 21:49:28";}";'
categories:
  - Microsoft
  - 電腦小貼事 Computing Tips and Tricks
---
整體上IE9 給我的感覺真是十分順暢&#8230;  
為了更加了解IE9 和其他瀏覽器 的速度有多小的分別&#8230;  
很多時候&#8230;只用眼去看..未必可以見到真正的結果的..  
所以便找了一個網站&#8221;**SunSpider JavaScript Benchmark**&#8221;  
用來測試**IE9 Beta**, **FireFox 3.6.10** 和 **Google Chrome 6.0.472.62**  
執行**JavaScript** 時的

我的電腦是**Windows Vista Utlimate 32 bits** **Centrino Duo 2.2Ghz**, **3GB Ram** GeForce 8600GT 256 MB Graphic

**Google Chrome 的結果是**  
**總共用了 376.4ms** +/- 4.6%  
3d:                    58.0ms +/- 21.0%  
access:                53.4ms +/- 39.3%  
bitops:                33.2ms +/- 6.7%  
controlflow:            3.2ms +/- 32.5%  
crypto:                23.0ms +/- 5.4%  
date:                  34.6ms +/- 8.7%  
math:                  46.4ms +/- 33.4%  
regexp:                14.6ms +/- 9.7%  
string:               110.0ms +/- 17.0%

**FireFox**  
**總共用了 1070.8ms** +/- 7.7%  
3d:                   169.0ms +/- 9.3%  
access:               171.8ms +/- 29.6%  
bitops:                44.2ms +/- 10.6%  
controlflow:           43.0ms +/- 10.2%  
crypto:                56.2ms +/- 8.6%  
date:                 165.0ms +/- 9.2%  
math:                  57.0ms +/- 6.0%  
regexp:                62.8ms +/- 11.5%  
string:               301.8ms +/- 7.6%

**IE9 Beta**  
**總共用了 505.4ms** +/- 1.9%  
3d:                    86.6ms +/- 26.1%  
access:                51.8ms +/- 6.7%  
bitops:                25.0ms +/- 3.5%  
controlflow:            3.4ms +/- 32.7%  
crypto:                28.0ms +/- 12.9%  
date:                  72.4ms +/- 9.0%  
math:                  44.2ms +/- 7.8%  
regexp:                34.8ms +/- 28.7%  
string:               159.2ms +/- 6.7%

始終都是**Google Chrome** 在處理**Javascript 的程序技勝一疇**  
**IE9 和 Chrome**的時間不是差得很遠..  
但是我最常用的 **FireFox** 郤用 了多一倍的時間來運行&#8230;

有機會待我測試一下**FireFox 4 Beta** 看看會不會像**IE9** 一樣快 =)

突然又發現一個 **IE9 Beta**&#8230;有待改進的 功能&#8230;  
就是在**Developer Tools** 上的&#8221;**Find**&#8221; -> &#8220;**Select Element By Click**&#8221;  
這個功能..是當你啟用了他後&#8230; 你便可以在網頁上選擇你想參考的 Element 看看他的HTML/CSS code&#8230; 每當你選擇了一個Element 後..又想再查看另一個Element 時 你便要再一次選擇**Developer Tools** 上的&#8221;**Find**&#8221; -> &#8220;**Select Element By Click**&#8221; 去啟動這功能  
[<img title="inspector" src="https://i1.wp.com/farm6.static.flickr.com/5246/5687824305_3e166fd606.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5246/5687824305_3e166fd606.jpg)

如果可以有一個功能可以當你Move Over 網頁的 **DOM/Element** 時  
便可以在**Developer Tools** 下面的**HTML/CSS/Script Section**  
顯示相關的**Element/Code** 就好了  
這對分析/學習網頁設計有很大的幫助

What do you think?