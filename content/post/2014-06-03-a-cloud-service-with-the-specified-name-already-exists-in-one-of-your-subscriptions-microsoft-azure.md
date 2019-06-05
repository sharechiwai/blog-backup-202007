---
id: 3209
title: 'A cloud service with the specified name already exists in one of your subscriptions &#8211; Microsoft Azure'
date: 2014-06-03T00:00:19+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3209
permalink: /2014/06/a-cloud-service-with-the-specified-name-already-exists-in-one-of-your-subscriptions-microsoft-azure/
categories:
  - Microsoft Azure
tags:
  - Microsoft Azure Troubleshooting
---
當我嘗試使用**Microsoft Azure** 來建立**Virtual Machine**時  
嘗試使用一個之前已刪除的**Virtual Machine**用過的**DNS** 名稱時 出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>A cloud service with the specified name already exists in one of your subscriptions</strong></span>&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5548/14243126100_2f4866e9b5_z.jpg?resize=625%2C433" alt="A cloud service with the specified name already exists in one of your subscriptions" width="625" height="433" data-recalc-dims="1" />  
[之前是因為選擇了比較遠的**Region**但是好像在**Azure**的**Config**上不能改變**VM** 的**Region**所以便決定刪除後從新再安裝]

做了一會research 之後發現..  
原來當你在**Azure**上建立**Virtual Machine**的時候.  
他會自動幫你建立一個**Cloud Service**的..  
但當你刪除這個**Virtual Machine**時..他又不會自動幫你刪除這個**Cloud Service**  
所以當我嘗試建立新的**VM** 時使用同一個**DNS** 名稱時便會出現  
&#8220;<span style="color: #ff0000;"><strong>A cloud service with the specified name already exists in one of your subscriptions</strong></span>&#8221;

**解決方法**十分簡單  
我們只需要按左選的選單上的&#8221;**Cloud Serivces**&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm6.static.flickr.com/5476/14429723005_1c20122985_z.jpg?resize=625%2C418" alt="Microsoft Azure Cloud Services" width="625" height="418" data-recalc-dims="1" /> 

之後選擇需要刪除的&#8221;**Cloud Services**&#8220;便可以了  
<img class="alignnone" src="https://i1.wp.com/farm4.static.flickr.com/3880/14429723215_f69924d58a_z.jpg?resize=625%2C128" alt="Successfully deleted Cloud Service" width="625" height="128" data-recalc-dims="1" /> 

之後便可以再次建立**Virtual Machine**了  
<img class="alignnone" src="https://i0.wp.com/farm6.static.flickr.com/5499/14243120388_8103829a92_z.jpg?resize=625%2C335" alt="Microsoft Azure Create Virtual Machine" width="625" height="335" data-recalc-dims="1" /> 

Hope you find it useful