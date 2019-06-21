---
id: 3911
title: 'C# check if String is null or empty - Learning from Code Review'
date: 2017-03-15T00:00:26+08:00
author: ShareChiWai
layout: post
categories:
  - Best Practices / 最佳實踐方法
tags:
  - 'C#'
  - Code Review
  - Learning from Code Review
---

最近的工作主要是做**Backend API** Library
今日有一個功能..
使用者的 input 需要輸入一些東西
不能是' ' **empty space**
所以便要做一些 validation 去檢查
以下是我的垃圾寫法

**code review** 後 同事建議了另一寫法給我
我覺得很好用的 簡單又容易明
**Code Review**前
[<img class="alignnone size-large wp-image-3913" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/BadSample.png?resize=625%2C727" alt="Silly way to check if string is not null and is not empty" width="625" height="727" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/BadSample.png)

```Csharp
string input = null;

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
```

**Code Review** 後的寫法
用了**String.IsNullOrWhiteSpace**來檢查這個 variable 有沒有字串

```csharp
string input = null;

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
```

<img class="alignnone size-large wp-image-3914" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/good-function.png?resize=625%2C740" alt="clearer way to check if string is not null and is not empty" width="625" height="740" />
Hope you find it useful
