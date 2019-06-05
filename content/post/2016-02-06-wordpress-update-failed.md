---
id: 3590
title: WordPress Update Failed
date: 2016-02-06T00:00:27+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3590
permalink: /2016/02/wordpress-update-failed/
categories:
  - WordPress
---
最近不知道為什麼用來做網誌的**WordPress** 不能自行更新  
每當有**新版本的Wordpress 發佈**後  
**WordPress**建議用戶更新  
可以當我嘗試使用他的更新按鈕時都會出現 一些錯誤  
相信是一些**permission**的設定問題  
做了很耐research都解決不到

最後請教了朋友..終於解決了  
解決方法

我們只需要在裝有**WordPress**的資料夾加上適當/正確的**權限**/所有者 **Owner** 便可

<pre>sudo chown -R www-data:www-data [web folder]
</pre>

Hope you find it useful