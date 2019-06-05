---
id: 1817
title: 'You are not authorized to view this page – HTTP Error 403.6 – Forbidden: IP address of the client has been rejected.'
date: 2011-06-02T00:00:25+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1817
permalink: '/2011/06/you-are-not-authorized-to-view-this-page-%e2%80%93-http-error-403-6-%e2%80%93-forbidden-ip-address-of-the-client-has-been-rejected/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
今日公司有同事在嘗試登入我們的Partner Website 時在瀏覽器上出現了以下的信息  
“**You are not authorized to view this page – HTTP Error 403.6 – Forbidden: IP address of the client has been rejected.**”  
<a href="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e445a1a735c1462984500304c0126b2d/renditions/fullsize.jpg" target="_blank"><img title="The Web server you are attempting to reach has a list of IP addresses that are not allowed to   access the Web site, and the IP address of your browsing computer is on this list" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e445a1a735c1462984500304c0126b2d/renditions/fullsize.jpg?resize=533%2C382" alt="" width="533" height="382" data-recalc-dims="1" /></a>

“The Web server you are attempting to reach has a list of IP addresses that are not allowed to  
access the Web site, and the IP address of your browsing computer is on this list.  
Please try the following:

Contact the Web site administrator if you believe you should be able to view this directory  
or page.  
HTTP Error 403.6 – Forbidden: IP address of the client has been rejected.  
Internet Information Services (IIS)”

之後發現原來公司上網的**IP Address** 因為我們升級了連線速度所以改變了  
由於這些網頁都要在他們的Server登記了**IP address**才可登入的  
所以便出現了這個問題的

**解決方法**  
聯絡Partner Website 向他們提供最新的IP Address..  
或聯絡你的**ISP**看看能不能用回之前的 IP Address

Hope you find it useful

&nbsp;