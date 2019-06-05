---
id: 889
title: 'Codeigniter &#8212; Unable to locate the model you have specified: sharechiwai_model'
date: 2010-11-03T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=889
permalink: /2010/11/codeigniter-unable-to-locate-the-model-you-have-specified-sharechiwai_model/
categories:
  - PHP 新手筆記
---
最近又開始繼續學習Codeigniter&#8230;  
我在**WIN VISTA** 上 安裝了 **XAMPP**, 用他來作我的**Web Server**  
花了一段時間後終於完成了一個 十分簡單的 Website&#8230;  
但當我發佈**Web Hosting** **的 Server** 上時&#8230;  
出現這個 錯誤信息&#8230;  
<span style="color: #ff0000;"><strong>&#8220;Unable to locate the model you have specified: sharechiwai_model&#8221;</strong></span>

我在自己的電腦上測試過是沒有問題的..  
最後發現&#8230;原來&#8230;**Codeigniter 的Model/Controller** 的檔案名是需要使用**Lower Case 的**&#8230; E.G. sharechiwai\_model&#8230; 當你的檔案名是ShareChiWai\_Model 時便會出現問題了  
在Linux 的Server 上由於是Case Sensetive 所以便不能找到正確的檔案名了&#8230;

如果你現在開始使用**Codeigniter Framework** 寫 **PHP** 的話..我會建議所有的檔案名都用Lower Case 來寫

Hope you find it useful