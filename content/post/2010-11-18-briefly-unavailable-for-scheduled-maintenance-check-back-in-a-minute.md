---
id: 978
title: 'Briefly unavailable for scheduled maintenance. Check back in a minute. &#8211; WordPress'
date: 2010-11-18T00:00:32+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=978
permalink: /2010/11/briefly-unavailable-for-scheduled-maintenance-check-back-in-a-minute/
categories:
  - WordPress
---
今天在使用 **WordPress** 的功能 自動更新**Plugin** 其間瀏覽器 [Chrome] 突然 Hang 機&#8230; 之後當我再次Load 我的網誌時便出現了以下的信息

&#8220;<span style="color: #ff0000;"><strong>Briefly unavailable for scheduled maintenance. Check back in a minute</strong></span>&#8221;

[<img class="alignnone size-full wp-image-979" title="WordPressMaintenance" src="https://i1.wp.com/farm6.static.flickr.com/5286/5687869623_0207673633.jpg?w=625" alt="" data-recalc-dims="1" />](https://i1.wp.com/farm6.static.flickr.com/5286/5687869623_0207673633.jpg)

我等了一段時間..但是還是只能看到這一頁&#8230; 最後便登入**FTP** 看看會不會是Server 出現問題..或我的**WordPress**檔案在更新是出現問題..所以我的檔案被刪除了等等&#8230;  
之後便看到有一個檔案叫 &#8220;**.maintenance**&#8220;[<img class="alignnone size-full wp-image-1005" title="FTPMaintenance" src="https://i0.wp.com/farm6.static.flickr.com/5150/5688398564_6ba924b2be.jpg?w=625" alt="" data-recalc-dims="1" />](https://i0.wp.com/farm6.static.flickr.com/5150/5688398564_6ba924b2be.jpg)

**解決方法是:**  
刪除這個 &#8220;**.maintenance**&#8221; 檔案..我的網誌便回復正常了

Hope you find it useful