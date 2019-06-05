---
id: 2948
title: '.Net Replace Non alphanumeric characters from a string  &#8211; .Net 上如何取代不是英文數字的 字串'
date: 2013-10-06T00:00:06+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2948
permalink: '/2013/10/net-replace-non-alphanumeric-characters-from-a-string-net-%e4%b8%8a%e5%a6%82%e4%bd%95%e5%8f%96%e4%bb%a3%e4%b8%8d%e6%98%af%e8%8b%b1%e6%96%87%e6%95%b8%e5%ad%97%e7%9a%84-%e5%ad%97%e4%b8%b2/'
categories:
  - .Net Tips And Tricks
---
今天其中一個工作是需要使用客戶的聯絡人名稱來建立新的用戶  
由於資料上他們的聯絡人名稱欄有些不是英文的字..  
有時有&#8221;**.**&#8220;, &#8220;**#**&#8220;, &#8220;**&#8211;**&#8221;  
所以建立用戶名稱時可能會出現錯誤..  
為了減低出現錯誤的機會..我決定找個方法取代這些不是數字或英文字母的文字

**如何取代字串中不是英文或數字的文字呢?**

做了一會兒**research** 之後終於找到了解決方法  
我們可以使用 **Regular Expression** 來設定一個 Rule 非英文或數字規則  
之後用他的**Replace** 功能去**Replace**這些文字便可以了

我建立了一個小小的功能.

**解決方法**:

[csharp]  
private readonly Regex rgxNonAlphaNumeric = new Regex("[^a-zA-Z0-9]");  
private string ReplaceNonAlphanumericChar(string sourceString, string replaceString = "")  
{  
return this.rgxNonAlphaNumeric.Replace(sourceString, replaceString);  
}

MessageBox.Show(ReplaceNonAlphanumericChar("abc%$672"));  
[/csharp]

Hope you find it useful