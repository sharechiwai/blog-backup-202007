---
id: 3272
title: 'Ionic &#8211; Preview Application on Browser &#8211; 怎樣預覽Ionic Framework 的程式'
date: 2014-07-07T00:00:45+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3272
permalink: '/2014/07/ionic-preview-application-on-browser-%e6%80%8e%e6%a8%a3%e9%a0%90%e8%a6%bdionic-framework-%e7%9a%84%e7%a8%8b%e5%bc%8f/'
categories:
  - Ionic Framework
tags:
  - ionic troubleshooting
---
終於開始了嘗試使用**Ionic Framework** 來開發 **Hybrid** 程式

開發方法是使用**HTML5 Javascript**和**CSS**  
所以我估計可以直接開啟 **Ionic Project** 資料夾上的 **html**檔案便可以看到程式的介面大概是怎樣的

誰不知 開啟 **index.html**後他只出現空白的畫面

那麼我們可以怎樣預覽我們用**HTML/JS** 寫出來的程式 **Layout** 呢  
做了一會research 之後發現  
原來原本的**Ionic Framewor**k是有教的..  
<a title="Ionic Framework Tutorial -> Test your application" href="http://ionicframework.com/docs/guide/testing.html" target="_blank">http://ionicframework.com/docs/guide/testing.html</a>

**解決方法**:  
我們只需要使用**NodeJs**的**console**到想預覽的**Ionic Application**的主目錄上  
輸入

<pre>ionic serve
</pre>

<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5590/14824797245_507a47b4d8_z.jpg?resize=625%2C127" alt="ionic serve command to preview your Ionic Framework application" width="625" height="127" data-recalc-dims="1" /> 

之後便可以在瀏覽器上預覽你的**hybrid**程式了

在輸入完指令後他便會輸出網址到**console**上  
你可以在瀏覽器上輸入那個網址來預覽[如果你的**browser**不會自動開啟的話]  
<img class="alignnone" src="https://i1.wp.com/farm3.static.flickr.com/2936/14638089190_c900d89be6_z.jpg?resize=400%2C565" alt="Ionic Application - Tabs Sample App" width="400" height="565" data-recalc-dims="1" /> 

Happy coding