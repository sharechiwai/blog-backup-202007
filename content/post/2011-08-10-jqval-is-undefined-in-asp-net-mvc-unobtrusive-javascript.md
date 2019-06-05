---
id: 1979
title: $jQval is undefined in ASP.Net MVC unobtrusive Javascript
date: 2011-08-10T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1979
permalink: /2011/08/jqval-is-undefined-in-asp-net-mvc-unobtrusive-javascript/
categories:
  - ASP.Net MVC
tags:
  - ASP.Net MVC
  - asp.net mvc client side validation
  - unobtrusive Javascript
  - validation
---
當我嘗試使**ASP.Net MVC**中的很放便的**Client Side Validation with unobtrusive Javascript** 時  
不知道為什麼我跟隨著教學 在**Web.config**上的**Application Setting**加入了

<pre>&lt;appSettings&gt;
    &lt;add key="ClientValidationEnabled" value="true"/&gt;
    &lt;add key="UnobtrusiveJavaScriptEnabled" value="true"/&gt;
  &lt;/appSettings&gt;</pre>

但是我的**ASP.Net MVC Application** 還是不會自己進行**Client Side Validation**  
之後在**firefox** 上嘗試找出原因時..  
卻看到有一個**Javascript**的Error..

&#8220;**<span style="color: #ff0000;">$jQval is undefined in Scripts/jquery.validate.unobtrusive.js</span>**&#8221;  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/64de14ae33784916b14d2631672a8d77/renditions/fullsize.jpg?resize=625%2C171" alt="$jQval is undefined in Scripts/jquery.validate.unobtrusive.js" width="625" height="171" data-recalc-dims="1" /> 

重複看了很多次的教學..卻找不到出現問題的地戶..

最後找了朋友幫忙看看..  
終於找到了我的錯誤了

**解決方法**:  
原來我加入了**jquery validation.unobtrusive** 的**Library**  
但是忘了加入 **validate** 的Library  
**E.G.**  
**<span style="color: #008080;"><script src=&#8221;@Url.Content(&#8220;~/Scripts/jquery.validate.min.js&#8221;)&#8221; type=&#8221;text/javascript&#8221;></script></span>**  


有問題的Import  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/5232e132a1074253b94f863b7df0730b/renditions/fullsize.jpg?resize=625%2C55" alt="unobtrusive Javascript not working" width="625" height="55" data-recalc-dims="1" /> 

解決了問題的Import

<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e858e038318441769896733d08c85043/renditions/fullsize.jpg?resize=625%2C62" alt="unobtrusive Javascript fixed" width="625" height="62" data-recalc-dims="1" /> 

Hope you find it useful