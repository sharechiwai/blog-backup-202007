---
id: 3911
title: 'C# check if String is null or empty &#8211; Learning from Code Review'
date: 2017-03-15T00:00:26+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3911
permalink: /2017/03/c-check-if-string-is-null-or-empty-learning-from-code-review/
categories:
  - Best Practices / 最佳實踐方法
tags:
  - 'C#'
  - Code Review
  - Learning from Code Review
---
最近的工作主要是做**Backend API** Library  
今日有一個功能..  
使用者的input需要輸入一些東西  
不能是&#8217; &#8216; **empty space**  
所以便要做一些validation 去檢查  
以下是我的垃圾寫法

**code review** 後 同事建議了另一寫法給我  
我覺得很好用的 簡單又容易明  
**Code Review**前  
[<img class="alignnone size-large wp-image-3913" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/BadSample.png?resize=625%2C727" alt="Silly way to check if string is not null and is not empty" width="625" height="727" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/BadSample.png?resize=880%2C1024 880w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/BadSample.png?resize=258%2C300 258w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/BadSample.png?resize=768%2C894 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/BadSample.png?resize=624%2C726 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/BadSample.png?w=1194 1194w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/BadSample.png)

<pre>string input = null;

if (input == null || input.Trim() == "")
{
	Console.WriteLine("Input is null or empty");
}
else
{
	Console.WriteLine("Input isvalid");
}
input = " ";
if (input == null || input.Trim() == "")
{
	Console.WriteLine("Input is null or empty");
}
else
{
	Console.WriteLine("Input isvalid");
}

input = " Yeah";
if (input == null || input.Trim() == "")
{
	Console.WriteLine("Input is null or empty");
}
else
{
	Console.WriteLine("Input isvalid");
}



</pre>

**Code Review** 後的寫法  
用了<span style="color: #008000;"><strong>String.IsNullOrWhiteSpace</strong> </span>來檢查這個variable 有沒有字串

<pre>string input = null;

if (String.IsNullOrWhiteSpace(input))
{
	Console.WriteLine("Input is null or empty");
}
else
{
	Console.WriteLine("Input is valid");
}

input = " ";
if (String.IsNullOrWhiteSpace(input))
{
	Console.WriteLine("Input is null or empty");
}
else
{
	Console.WriteLine("Input is valid");
}

input = " Yeah";
if (String.IsNullOrWhiteSpace(input))
{
	Console.WriteLine("Input is null or empty");
}
else
{
	Console.WriteLine("Input is valid");
}



</pre>

<img class="alignnone size-large wp-image-3914" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/good-function.png?resize=625%2C740" alt="clearer way to check if string is not null and is not empty" width="625" height="740" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/good-function.png?resize=865%2C1024 865w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/good-function.png?resize=253%2C300 253w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/good-function.png?resize=768%2C909 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/good-function.png?resize=624%2C739 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/good-function.png?w=1163 1163w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
Hope you find it useful