---
id: 2842
title: PHP Get Client IP Address on OpenShift
date: 2013-03-30T00:00:47+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2842
permalink: /2013/03/php-get-client-ip-address-on-openshift/
categories:
  - OpenShift
---
今天嘗試在**Openshift**上 更新我的**GEO IP Location App**  
誰不知我使用的**PHP** 程式碼只能取後在**OpenShift**上的電腦的IP Address

[php]  
echo $\_SERVER[&#8216;REMOTE\_ADDR&#8217;];  
[/php]

做了一會兒Research 後終於找到了解決方法

**解決方法**:  
我們可以使用 **HTTP\_X\_FORWARDED_FOR** 來取得瀏覽的IP Address

[php]  
echo $\_SERVER[&#8216;HTTP\_X\_FORWARDED\_FOR&#8217;];  
[/php]

Hope you find it useful