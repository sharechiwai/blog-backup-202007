---
id: 212
title: .Net get Enum text from Enum or Get Enum Text from ENum Number
date: 2010-04-10T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/04/10/net-get-enum-text-from-enum-or-get-enum-text-from-enum-number
permalink: /2010/04/net-get-enum-text-from-enum-or-get-enum-text-from-enum-number/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "507046413992207133"
categories:
  - .Net Tips And Tricks
---
I am working on a web-service project, which has lots of property is set to use Enum. After I made a web-service call, some of the response properties is assigned by Enum value. I need to display the information to my windows application/web-site. When I show the value to the website, it displays the Enum number/integer rather then a string. 

At the end, I have worked out how to display the Enum string on to my application.

**Here it is my solution.**  
E.g. **EnumVariable** is the Enum that return by the web-service  
Instead of using 

<span style="font-size:x-small;"><b><span style="color:#0b5394;">txt_ToDisplay.Text = EnumVariable</span></b></span>  
Or  
<span style="color:#0b5394;font-size:x-small;"><b>txt_ToDisplay.Text = EnumVariable.Value</b></span>

You would need to use  
<span style="color:#38761d;font-size:x-small;"><b>txt_ToDisplay.Text = EnumVariable.toString()</b></span>

On the other hand, if you need to convert the **Enum Integer to Enum string**  
You can try the following.  
**VB.Net**  
<span style="font-size:x-small;"><b>DirectCast([Enum].Parse(GetType(EnumDataType), EnumVariable), EnumDataType)</b></span>  
**C#**  
<span style="font-size:x-small;"><b>(EnumDataType))Enum.Parse(typeof(EnumDataType)), EnumVariable);</b></span>

Hope your find it useful.