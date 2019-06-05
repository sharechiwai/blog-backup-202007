---
id: 1875
title: 'Codeigniter  &#8211; In order to use the Session class you are required to set an encryption key in your config file.'
date: 2011-06-26T00:00:16+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1875
permalink: /2011/06/codeigniter-in-order-to-use-the-session-class-you-are-required-to-set-an-encryption-key-in-your-config-file/
categories:
  - PHP 新手筆記
tags:
  - Codeigniter
---
最近又再一次好好地開始學習**Codeigniter**了  
當我跟隨著教學的步驟學習使用時  
出現了以下的錯誤信息

&#8220;<span style="color: #ff0000;"><strong>In order to use the Session class you are required to set an encryption key in your config file.</strong></span>&#8221;  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f72d15b73b7241f3a354e55f2130c19b/renditions/fullsize.jpg?resize=453%2C133" alt="" width="453" height="133" data-recalc-dims="1" />  
由於教學是以**Codeigniter 1.7.2**寫的關係..  
所以有些地方已經不同了

在**Codeigniter 2.0.0**或以後的更新時  
如果我們要使用**Session**這一個**Class**的話  
我們便要在<span style="color: #0000ff;"><strong>Conifg.php</strong></span> 中的 **<span style="color: #008000;">$config[&#8216;encryption_key&#8217;] =&#8221;&#8221;;</span>** 加上一個**encryption key**

**解決方法**  
打開你的**Codeigniter**資料來  
之後打開**<span style="color: #0000ff;">Application/Config/config.php</span>**  
在config.php 中 找出**<span style="color: #008000;">$config[&#8216;encryption_key&#8217;]</span>**  
之後 輸入 **encryption key** 便可  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/9b9b3af423ab4dc5a8d882106a072111/renditions/fullsize.jpg?resize=625%2C103" alt="" width="625" height="103" data-recalc-dims="1" />  
大家亦都可以複製少下的**Encryption key**

[php]  
$config[&#8216;encryption_key&#8217;] = &#8216;APANtByIGI1BpVXZTJgcsAG8GZl8pdwwa84&#8217;;  
[/php]

Hope you find it useful