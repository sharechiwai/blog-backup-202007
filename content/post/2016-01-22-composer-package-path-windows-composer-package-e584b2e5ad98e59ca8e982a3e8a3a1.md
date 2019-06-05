---
id: 3558
title: 'Composer Package Path Windows &#8211; Composer Package 儲存在那裡'
date: 2016-01-22T00:00:53+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3558
permalink: '/2016/01/composer-package-path-windows-composer-package-%e5%84%b2%e5%ad%98%e5%9c%a8%e9%82%a3%e8%a3%a1/'
categories:
  - Composer
tags:
  - Atom
  - Atom Plugins
  - Composer
  - Package Manager
---
有些程式需要我們在他的設定檔上加入 **Composer** 下載/安裝的 **Package Path**  
其實**Composer** 的**Package Path**在那裡呢?

在了一會research之後發現他們都在 以下的資料夾入

大家可以開啟任何的資料夾之後貼上以下的路徑 便可以找到這些Package了  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1501/24454716060_092afc8529_z.jpg?resize=625%2C180" alt="Enter Composer Package Path" width="625" height="180" data-recalc-dims="1" /> 

<pre>%APPDATA%\Composer\vendor\bin
</pre>

或是在

<pre>C:\Users\[Username]\AppData\Roaming\Composer\vendor\bin
</pre>

<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1480/24751709675_10b2c2311d_z.jpg?resize=625%2C218" alt="Composer Package Path" width="625" height="218" data-recalc-dims="1" />  
Hope you find it useful