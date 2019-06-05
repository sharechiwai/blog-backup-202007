---
id: 2303
title: 'Little tips about code formatting in C Sharp &#8211; C# Code Formatting 的小小貼事'
date: 2012-04-08T00:00:15+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2303
permalink: '/2012/04/little-tips-about-code-formatting-in-c-sharp-c-code-formatting-%e7%9a%84%e5%b0%8f%e5%b0%8f%e8%b2%bc%e4%ba%8b/'
categories:
  - .Net Tips And Tricks
---
今天參加了**Microsoft** 的 **Windows 8 Camp**  
入面有很多 **Lab**要學習..  
由於有很多**Lab Exercises**的關係  
所以沒有時候給我們自行逐一輸人所有程式碼&#8230;  
所以很多時候都是明白了要寫的程式碼..  
之後再把他們從**Exercise**上複製..之後貼上到**Visual Studio**上..再看效果&#8230;

由於現在很多**Training** 的 **material**都是使用**C Sharp**的關係..  
我也使用了**C Sharp**了  
之後發現到一個問題..  
就是當你使用複製/貼上 時有時候程式碼的格式/**Indentation**會出現不對齊的問題..  
看起來十分難看呢..  
使用**VB.Net**的話..程式碼是會自動格式化/對齊的 比較方便  
而在開發**ASP.Net**的朋友&#8230;  
在**ASP.Net**程式碼的頁面上&#8230; 遇到同一問題時:  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/59ff70c881304188a07d54805025c542" alt="asp.net source code not formatted" width="483" height="392" />  
大家亦都可以選擇一些程式碼  
之後右**Mouse** 右鍵->之後選擇&#8221;**Format Selection**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/b1cef57690bb4ff1aaa74c71915c3fea" alt="asp.net format selection" width="763" height="451" />  
格式排位後便變成很整齊了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2ad3e1bfeb0a404188e69ad929233f42" alt="ASP.Net source code formatted" width="518" height="383" /> 

在**CSharp**沒有這麼好的功能..  
但是我今天發現了一個很簡單..方便的**解決方法**&#8230;希望大家喜歡  
以下是我之前用複製/貼上 到**Visual Studio**上 的程式碼..  
他的排位有一點亂..  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/549a2ad7c7374e1fa27ae884d0396149" alt="Code Identation Before" width="745" height="380" />  
**解決方法**:  
我們只要把程式碼的**function**最後一個**curly bracket** &#8220;**}**&#8220;刪除.. 之後再次輸入這個**curly bracket** 便可以了 &#8220;**}**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/84c34a79299b416dae8e03c5feb4e384" alt="Code Identation fixed" width="714" height="377" />  
Hope you find it useful