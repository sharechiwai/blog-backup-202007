---
id: 3150
title: 'C Sharp String Split by New Line Character &#8211; C# 上如何把字串以新行字串分開 &#8211; The best overloaded method match for &#8216;string.Split(params char[])&#8217; has some invalid arguments'
date: 2014-04-22T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3150
permalink: '/2014/04/c-sharp-string-split-by-new-line-character-c-%e4%b8%8a%e5%a6%82%e4%bd%95%e6%8a%8a%e5%ad%97%e4%b8%b2%e4%bb%a5%e6%96%b0%e8%a1%8c%e5%ad%97%e4%b8%b2%e5%88%86%e9%96%8b-the-best-overloaded-method-match/'
categories:
  - .Net Tips And Tricks
---
今天在公司上寫一個新的**feature**給使用者把資料輸入到一個  
**Mutli-line** 的**TextBox**上  
之後便可以一次過加入所有輪入的數據了

嘗試使用 <span style="color: #008000;"><strong>String.Split(Environment.NewLine)</strong></span>

[csharp]  
input.Split(Environment.NewLine)  
[/csharp]

可惜出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>The best overloaded method match for &#8216;string.Split(params char[])&#8217; has some invalid arguments</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7328/13941926907_61d09aaf15_z.jpg?resize=625%2C94" alt="The best overloaded method match for 'string.Split(params char[])' has some invalid arguments" width="625" height="94" data-recalc-dims="1" /> 

**解決方法**十分簡單:  
我們可以把<span style="color: #008000;"><strong>Environment.NewLine</strong></span>轉成 Char Array便可以了

**E.G.**

[csharp]  
string input = textBox1.Text;  
List<string> inputList = input.Split(Environment.NewLine.ToCharArray()).ToList();  
[/csharp]

Hope you find it useful