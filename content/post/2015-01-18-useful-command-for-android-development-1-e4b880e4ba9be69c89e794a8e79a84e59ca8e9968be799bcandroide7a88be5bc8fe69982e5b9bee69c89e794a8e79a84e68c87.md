---
id: 3374
title: 'Useful command for Android Development 1 &#8211; 一些有用的在開發Android程式時幾有用的指令筆記'
date: 2015-01-18T00:00:31+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3374
permalink: '/2015/01/useful-command-for-android-development-1-%e4%b8%80%e4%ba%9b%e6%9c%89%e7%94%a8%e7%9a%84%e5%9c%a8%e9%96%8b%e7%99%bcandroid%e7%a8%8b%e5%bc%8f%e6%99%82%e5%b9%be%e6%9c%89%e7%94%a8%e7%9a%84%e6%8c%87/'
categories:
  - Android
tags:
  - ionic
---
最近多了開發**Android**程式..  
發現有很多時候..有一些幾長的指令..  
常常在準備發佈  
一些有用的 **android development command** 記下便可以在這裡複製了..  
不用自己打 =)

發現做程式開發很多時候都需要**sign key**

以下便是**建立 Sign Key的 指令**..  
只是把 **[ 的內容/名字 ]**更變了便可以用來Generate 自己的Sign key

我通常會把我的**key** 方在同一個地方上..方便搵  
E.g

<pre>D:\Ionic\SampleProject\keystores
</pre>

之後便用**command prompt** 開啟這個資料夾..

<pre>keytool -genkey -v -keystore [my-release-key.keystore/你的Release Key的名.keystore] -alias [alias_name/別名] -keyalg RSA -keysize 2048 -validity 10000
</pre>

然後輸入以下指令  
**e.g.**

<pre>keytool -genkey -v -keystore SharechiwaiDemoReleaseKey.keystore -alias ShareChiWaiDemoReleaseKey -keyalg RSA -keysize 2048 -validity 10000
</pre>

之後便會要求你輸入一個密碼給這個**keystore  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7423/16176438129_1d54901293_z.jpg?resize=625%2C121" alt="Keytools - Generate Key Step 1" width="625" height="121" data-recalc-dims="1" />**  
完成後會叫你輸入一些資料給這個**keystore** e.g. 你的名稱/ 公司名和地區等等

之後會叫你確認之前輸入的資料  
如果沒有問題的話..輸入&#8221;**yes**&#8221;  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7317/16175036718_652eae6fe1_z.jpg?resize=625%2C392" alt="Keytools Confirm Key Information" width="625" height="392" data-recalc-dims="1" /> 

他會再叫你輸入一個新的密碼 給這個 key  
如果想使用和**keystore**一樣的密碼..可以按&#8221;**Enter**&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm9.static.flickr.com/8609/16175036698_7607366497_z.jpg?resize=625%2C235" alt="keytools - confirm key password" width="625" height="235" data-recalc-dims="1" /> 

之後便完成了 Generate Release Key 這個動作了

<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7356/16176768317_9b2f2b66d9_z.jpg?resize=625%2C69" alt="keystore file" width="625" height="69" data-recalc-dims="1" />  
Hope you find it useful