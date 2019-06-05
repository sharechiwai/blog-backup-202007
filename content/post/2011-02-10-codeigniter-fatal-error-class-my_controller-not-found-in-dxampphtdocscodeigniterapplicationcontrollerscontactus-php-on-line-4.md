---
id: 1268
title: 'CodeIgniter Fatal error: Class &#8216;MY_Controller&#8217; not found in D:xampphtdocsCodeIgniterapplicationcontrollerscontactus.php on line 4'
date: 2011-02-10T00:00:48+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1268
permalink: /2011/02/codeigniter-fatal-error-class-my_controller-not-found-in-dxampphtdocscodeigniterapplicationcontrollerscontactus-php-on-line-4/
categories:
  - Codeingter
---
在嘗試寫一個Override Controller 之後  
當我嘗試Refresh我的Web Page 時出現了這個錯誤信息  
[<img class="alignnone" title="Fatal error: Class 'MY_Controller' not found in D:xampphtdocsCodeIgniterapplicationcontrollerscontactus.php on line 4" src="https://i1.wp.com/farm5.static.flickr.com/4116/5441338616_c604f05523.jpg?resize=500%2C228" alt="Fatal error: Class 'MY_Controller' not found in D:xampphtdocsCodeIgniterapplicationcontrollerscontactus.php on line 4" width="500" height="228" data-recalc-dims="1" />](https://i1.wp.com/farm5.static.flickr.com/4116/5441338616_c604f05523.jpg)  
&#8220;**Fatal error: Class &#8216;MY_Controller&#8217; not found in D:xampphtdocsCodeIgniterapplicationcontrollerscontactus.php on line 4**&#8221;

之後發現原來是因為我的**Controller**嘗試**Extends** 一個自己更改過的**Controller**..[**MY_Controller**]

而我把這個**MY_Controller** 放錯了在 **Library** folder 入面&#8230;

解決方法:  
只要把這個自定的**Controller [MY_Controller]**放進在 application 資料夾便可  
<span style="color: #008000;"><strong> D:xampphtdocsCodeIgniterapplicationcoreMY_Controller.php</strong></span>

Hope you find it useful