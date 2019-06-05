---
id: 1919
title: 'ASP.Net MVC Set Default browser &#8211; ASP.Net MVC 設定預設瀏覽器'
date: 2011-07-23T00:00:01+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1919
permalink: '/2011/07/asp-net-mvc-set-default-browser-asp-net-mvc-%e8%a8%ad%e5%ae%9a%e9%a0%90%e8%a8%ad%e7%80%8f%e8%a6%bd%e5%99%a8/'
categories:
  - ASP.Net MVC
tags:
  - VS2010 Set Default Browser
---
由於**ASP.Net MVC 和傳統的ASP.Net Application** 其中一個很大不同的地方是  
**ASP.Net MVC 很多時候都要自己寫一些Javascript來做一些行動**..  
由於自己對**Javascript**不太熟識的關係..  
很多時候都會出現**Javascript/CSS**的錯誤..  
如果沒有發現到..便會花很多時間來測試這個**ASP.Net MVC Application**  
但是又留意不到問題原來是**Javascript**上忘了加上&#8221;**; ) 或]** }&#8221;

所以每當我要開發**Web Application** 時..我比較喜歡**使用FireFox 和FireBug**的..  
可能我很久之前的習慣吧  
但是我又感覺到**FireFox始終都沒有Google Chrome 和IE9 那麼Light-Weight和快**..  
所以我的**預設的Browser是Google Chrome**&#8230;

現在每當我嘗試Debug我的**ASP.Net MVC Application**是..他都會使用我**預設的Browser** [**Google Chrome**] &#8230;為了方便自己Debug Javascript..所以我便嘗試在**Visual Studio**上更改預設Debug的Browser 了.. 還記得在**Visual Studio更改預設的Browser** 是很方便的.. 只要在任何一個**.aspx** 或 **.html**上按右鍵..->選擇 &#8220;**Browse With..**&#8221; 之後選擇自己想用的Browser便可以了..

當我嘗試在**MVC Application** 上的其中一個**View**做同一個動作時  
E.G.在 **cshtml上按右鍵 卻看不到有 &#8220;Browse With..&#8221;** 這個選項..  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/5e53cba9a0db47fdb4e7601aa7970dc9/renditions/fullsize.jpg?resize=490%2C484" alt="" width="490" height="484" data-recalc-dims="1" /> 

最後終於找到解決的方法了

**解決方法:**  
我們只要在這個**ASP.Net MVC Application上建立一個 Web Form** E.g. .**aspx**的檔案.. 之後在他上面按右鍵..->選擇 &#8220;**Browse With..**&#8221; 之後選擇自己想用的**Browser**便可以了

在**Project**上按右鍵..選擇&#8221;**Add/新增**&#8221; -> &#8220;**New Item&#8230;/新增項目**&#8221;  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/b4db53ddb987421e83e0bc8f3fd569b8/renditions/fullsize.jpg?resize=619%2C733" alt="" width="619" height="733" data-recalc-dims="1" /> 

在&#8221;**Add New Item/新增項目**&#8220;視窗中選擇 **&#8220;Web Form**&#8220;..之後按&#8221;**OK/確定**&#8221;  
<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/afef0a5ddf524acd972caaa1186b9ecb/renditions/fullsize.jpg?resize=625%2C333" alt="" width="625" height="333" data-recalc-dims="1" /> 

i之後我們便可以在這個新增的&#8221;**.aspx**&#8220;檔案上按右鍵..->選擇 &#8220;**Browse With..**&#8221; [這次我們終於見到了&#8221;**Browse With&#8230;**&#8220;這個選項了]  
<img src="https://i1.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/6b9c75617c3e48b3bfbf5cf34ab71459/renditions/fullsize.jpg?resize=608%2C593" alt="" width="608" height="593" data-recalc-dims="1" /> 

在&#8221;**Browse With**&#8221; 視窗中 我們可以選擇用那一個瀏覽器 作為**預設瀏覽** 我們**Debug**時的Web Application..選擇了之後我們可以按一下**&#8220;Set as Default/設定為預設**&#8221; 便可以了  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/4acea775f4614cc2bf0c9ac0951129f6/renditions/fullsize.jpg?resize=488%2C372" alt="" width="488" height="372" data-recalc-dims="1" /> 

現在每當執行這個**ASP.NET MVC Application** 時 **FireFox會啟動為預設瀏覽器**了  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8814ac265e4b489cb7ddc5521bdaf50a/renditions/fullsize.jpg?resize=497%2C442" alt="" width="497" height="442" data-recalc-dims="1" /> 

之後我們可以刪除之前建立的&#8221;**.aspx**&#8221; 檔案

Hope you find it useful