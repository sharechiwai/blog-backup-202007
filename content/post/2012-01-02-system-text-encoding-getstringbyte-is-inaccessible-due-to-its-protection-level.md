---
id: 2210
title: '&#8216;System.Text.Encoding.GetString(byte[])&#8217; is inaccessible due to its protection level'
date: 2012-01-02T00:00:34+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2210
permalink: /2012/01/system-text-encoding-getstringbyte-is-inaccessible-due-to-its-protection-level/
categories:
  - Silverlight Tips and Tricks
tags:
  - .Net Troubleshooting
---
今天嘗試在**Silverlight** 上把**Byte Array** 轉成**String**的時候出現了以下的錯誤信息  
<span style="color: #ff0000;"><strong>Error 1 &#8216;System.Text.Encoding.GetString(byte[])&#8217; is inaccessible due to its protection level</strong></span>  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e2177a1e238346d2bacc970575313f2a" width="670" height="73" alt="'System.Text.Encoding.GetString(byte[])' is inaccessible due to its protection level" />  
**  
CSharp**

[csharp]  
byte[] StringAsByteArray = Convert.FromBase64String(source);  
string OriginalStringText = Encoding.UTF8.GetString(StringAsByteArray);  
return OriginalStringText;  
[/csharp]

經過一會兒的Research之後找到了解決的方法了

**解決方法** 十分簡單

我們需要用以下的Code去把Byte 讀出來  
**CSharp**

[csharp]  
string OriginalStringText = Encoding.UTF8.GetString(StringAsByteArray,0, StringAsByteArray.Length);  
[/csharp]

Hope you find it useful