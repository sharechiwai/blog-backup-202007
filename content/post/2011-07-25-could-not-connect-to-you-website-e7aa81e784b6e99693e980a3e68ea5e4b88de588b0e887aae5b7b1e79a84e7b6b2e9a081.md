---
id: 1891
title: 'Could not connect to you website&#8230;突然間連接不到自己的網頁'
date: 2011-07-25T00:00:28+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1891
permalink: '/2011/07/could-not-connect-to-you-website-%e7%aa%81%e7%84%b6%e9%96%93%e9%80%a3%e6%8e%a5%e4%b8%8d%e5%88%b0%e8%87%aa%e5%b7%b1%e7%9a%84%e7%b6%b2%e9%a0%81/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
今天當我嘗試到我的網誌的時候發現連接不上..  
出現以下的錯誤信息..  
<img title="Could not connect to blog.sharechiwai.com" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a70557ce32ab4d9ab4a70bf9bff218cb/renditions/fullsize.jpg?resize=625%2C178" alt="Could not connect to blog.sharechiwai.com" width="625" height="178" data-recalc-dims="1" />  
之後我便看看朋友在同一個Server 上Host 的網頁有沒有問題..  
結果..所有網頁都是正常的..只有我的網誌有問題..

之後我便做了一些測試了..  
在**Windows** 上用**Command Prompt**上執行  
<span style="color: #008000;"><strong>nslookup blog.sharechiwai.com</strong></span>  
來檢查一下自己的**Name Server**是不是把我的網誌指向剛剛登記的Web Hosting上  
<img title="nslookup result for blog.sharechiwai.com...wrong IP address" src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0f6e8fad3d0844bc8a1f04dc93cd62ca/renditions/fullsize.jpg?resize=418%2C242" alt="nslookup result for blog.sharechiwai.com...wrong IP address" width="418" height="242" data-recalc-dims="1" />  
誰不知&#8230;我網誌的的IP address 結果是指向了一個 自己都沒有記憶的IP Address  
就是因為這樣子&#8230;我connect不到自己的網頁

之後我到了管理我domain name 我公司網頁上再一次檢查會不會是account被人**hack**了..  
所以被人轉了**Name server的address**

但是看過了settings 一切都是正常的..  
我便找朋友幫我試試是不是我的電腦的問題..  
所有朋友都說我的網誌沒有問題..  
之後我便懷疑 會不會是 ISP的問題  
最後我在**Router上改變了上網的DNS Server**便解決了問題了  
<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/575772fad8c54b0db630df8050c7b37d/renditions/fullsize.jpg?resize=605%2C332" alt="" width="605" height="332" data-recalc-dims="1" />  
我使用了**Google 的DNS Address**  
把DNS Address 轉成  
**<span style="color: #008000;">8.8.8.8</span>**  
和  
<span style="color: #008000;"><strong>8.8.4.4 <&#8211;這個在中國入都用到的 聽聞 8.8.8.8 是被封鎖了的</strong></span>

Please correct me if I am wrong  
之後再次使用**nslookup來檢查 網頁的IP Address**  
**問題解決**了  
<img title="nslookup blog.sharechiwai.com with the correct result" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/9c1fc1ba94f649ad9c2fb3b57371e6f1/renditions/fullsize.jpg?resize=439%2C147" alt="nslookup blog.sharechiwai.com with the correct result" width="439" height="147" data-recalc-dims="1" />  
還是不知道為什麼ISP 會把我的網誌指向了別一個IP Address

Hope you find it useful