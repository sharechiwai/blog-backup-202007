---
id: 3231
title: 'Android Rate Button &#8211; 如何建立Android 評分按鈕'
date: 2014-06-15T00:00:18+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3231
permalink: '/2014/06/android-rate-button-%e5%a6%82%e4%bd%95%e5%bb%ba%e7%ab%8bandroid-%e8%a9%95%e5%88%86%e6%8c%89%e9%88%95/'
categories:
  - Android
tags:
  - User Experience
---
最近到了一個電腦活動  
他們講解了鼓勵**Apps**使用者在你的**App**評分的重要性

所以使想到要為自己的程式更新..增加一個方便使用者**Rate This App**的功能  
做了一會Research很發現..

**解決方法**十分簡單  
我們可以建立一個功能.. 這可以方便將來重用&#8230;  
之後使用 <span style="color: #008000;"><strong>getPackageName</strong> </span>這個功能來取後這個程式的 **Namespace**  
再建立一個 **Google Play Store**的網址連結  
之後在用一個<span style="color: #008000;"><strong>Intent</strong></span>來關啟便可以了  
<img class="alignnone" src="https://i0.wp.com/farm3.static.flickr.com/2924/14698607031_1566051d02_z.jpg?resize=360%2C640" alt="Google Play Store - L Quiz UK" width="360" height="640" data-recalc-dims="1" /> 

E.G.

<pre>public void RateMyApp(){

  // 建立一個Intent - 在這個Intent 上使用 Google Play Store 的連結
  // E.G. market://details?id=
  // 之後用 getPackageName 這個功能來取後這個程式的 Namespace.
  Intent goToMarket = new Intent(Intent.ACTION_VIEW, Uri.parse("market://details?id=" + getPackageName()));
 
  try {
        // 之後開始一個新的Activity 去這個Intent
        startActivity(goToMarket);
  } catch (ActivityNotFoundException e) {
        // 如果有錯誤的話 使用正常的網址來連接到 Google Play Store的網頁
        startActivity(new Intent(Intent.ACTION_VIEW, Uri.parse("http://play.google.com/store/apps/details?id=" + getPackageName())));
  }
}
</pre>

大家有沒有嘗試過找的 <a title="L Quiz UK - Introduction" href="http://sharechiwai.com/apps/lquizuk" target="_blank"><strong>L Quiz UK</strong> </a>App 呢?  
<a title="L Quiz UK at Google Play Store" href="https://play.google.com/store/apps/details?id=com.sharechiwai.lquizuk" target="_blank">https://play.google.com/store/apps/details?id=com.sharechiwai.lquizuk<br /> <img class="alignnone" src="https://i0.wp.com/farm4.static.flickr.com/3881/14699387134_b225895604_z.jpg?resize=360%2C640" alt="L Quiz UK - About Page and Rate my App button" width="360" height="640" data-recalc-dims="1" /><br /> </a>

Hope you find it useful