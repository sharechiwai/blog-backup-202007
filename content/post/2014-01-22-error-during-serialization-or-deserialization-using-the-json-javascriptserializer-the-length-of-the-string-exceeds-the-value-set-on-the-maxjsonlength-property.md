---
id: 3006
title: Error during serialization or deserialization using the JSON JavaScriptSerializer. The length of the string exceeds the value set on the maxJsonLength property.
date: 2014-01-22T00:00:19+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3006
permalink: /2014/01/error-during-serialization-or-deserialization-using-the-json-javascriptserializer-the-length-of-the-string-exceeds-the-value-set-on-the-maxjsonlength-property/
categories:
  - .Net Tips And Tricks
tags:
  - .Net Troubleshooting
  - JSON
---
今天嘗試便用 **JavaScriptSerializer** 把公司一個資料庫的資料轉成 **Json** 放在公司的另一個程式上做**Performance Test**的時候出現以下的錯誤信

&#8220;**<span style="color: #ff0000;">An unhandled exception of type &#8216;System.InvalidOperationException&#8217; occurred in System.Web.Extensions.dll</span>**

**<span style="color: #ff0000;">Additional information: Error during serialization or deserialization using the JSON JavaScriptSerializer. The length of the string exceeds the value set on the maxJsonLength property.</span>**&#8221;  
<img class="alignnone" alt="Error during serialization or deserialization using the JSON JavaScriptSerializer. The length of the string exceeds the value set on the maxJsonLength property." src="https://i1.wp.com/farm8.staticflickr.com/7323/12346525195_9902186396_c.jpg?resize=625%2C122" width="625" height="122" data-recalc-dims="1" /> 

原因是因為我有太多資料..而預設的**Json** 字串大小是**2097152**個字元&#8230; 我的數據..文字比較多..  
便所以出現這個錯誤信息..  
解決方法 十分簡單..只是把 **Serializer** 的 **MaxJsonLength** 的值比你的 資料更大便可以了

**解決方法:**

E.G.

[csharp]  
// 建立 JavascriptSerializer Object  
System.Web.Script.Serialization.JavaScriptSerializer serializer = new System.Web.Script.Serialization.JavaScriptSerializer();  
// 查看 JavascriptSerializer Object的 Default MaxJsonLength 是什麼  
Console.WriteLine("Default MaxJsonLength value: " + serializer.MaxJsonLength.ToString());  
// 更新 JavascriptSerializer Object的 MaxJsonLength 大小&#8230; 為Integer的最大值..因為他是Int32的 DataType  
serializer.MaxJsonLength = Int32.MaxValue;  
Console.WriteLine("Updated MaxJsonLength value: " + serializer.MaxJsonLength.ToString());

[/csharp]

這應該可以解決這個問題

Hope you find it useful