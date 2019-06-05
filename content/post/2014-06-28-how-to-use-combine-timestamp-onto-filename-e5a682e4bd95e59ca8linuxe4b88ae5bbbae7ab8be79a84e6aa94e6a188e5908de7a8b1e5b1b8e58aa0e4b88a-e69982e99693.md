---
id: 3254
title: 'How to use combine timestamp onto filename &#8211; 如何在Linux上建立的檔案名稱加上 時間戳的值'
date: 2014-06-28T00:00:46+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3254
permalink: '/2014/06/how-to-use-combine-timestamp-onto-filename-%e5%a6%82%e4%bd%95%e5%9c%a8linux%e4%b8%8a%e5%bb%ba%e7%ab%8b%e7%9a%84%e6%aa%94%e6%a1%88%e5%90%8d%e7%a8%b1%e5%b1%b8%e5%8a%a0%e4%b8%8a-%e6%99%82%e9%96%93/'
categories:
  - Linux Notes / Linux 新手筆記
tags:
  - Ubuntu
---
在之前的網誌上介紹了如何在**Linux** 上建立/輸出一個**Timestamp**的值

### <a href="http://blog.sharechiwai.com/2014/06/linux-how-to-generate-current-timestampyyyymmddhhmmss-%e5%9c%a8linux-%e4%b8%ad%e5%bb%ba%e7%ab%8b%e4%b8%80%e5%80%8b%e5%83%8f%e6%99%82%e9%96%93%e6%88%b3%e7%9a%84%e5%80%bc/" rel="bookmark">Linux How to Generate Current Timestamp(yyyyMMddhhmmss) – 在Linux 中建立一個像時間戳的值</a> {.entry-title}

其實建立**Timestamp**的主要目的是為了在自己建立的**備份檔案**上的檔案名加上日期

**解決方法** 十分簡單我們只需要在想加入 **Timestamp**的檔案名稱位置上 加上  
<span style="color: #008000;"><strong><span style="color: #003300;">$(</span>date +%Y%m%d%H%M%S<span style="color: #003300;">)</span></strong> </span>便可以了

**E.G.**

<pre>nano backup_$(date +%Y%m%d%H%M%S).txt
</pre>

<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5572/14623218928_d3e09e39e6_z.jpg?resize=625%2C67" alt="Linux Create file with Current timestamp command" width="625" height="67" data-recalc-dims="1" />  
儲存這個**Nano** 檔案  
<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3887/14623302577_c65a427470_z.jpg?resize=625%2C394" alt="Save this Nano file" width="625" height="394" data-recalc-dims="1" /> 

查看這個**Directory**上有的檔案便會看到有一個檔案的名稱有一個像**TimeStamp**的東西  
<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3888/14786833246_1f18893ffd_z.jpg?resize=563%2C125" alt="Linux Check Directory" width="563" height="125" data-recalc-dims="1" /> 

Hope you find it useful