---
id: 332
title: '.Net Error &#8211; BadImageFormatException An attempt was made to load a program with an incorrect format.'
date: 2010-01-28T01:28:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/01/28/net-error-badimageformatexception-an-attempt-was-made-to-load-a-program-with-an-incorrect-format
permalink: /2010/01/net-error-badimageformatexception-an-attempt-was-made-to-load-a-program-with-an-incorrect-format/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4778882961188899178"
categories:
  - .Net Tips And Tricks
---
When i try to upgrade one of my application at work today from VS2005 to VS2008 I have received the following error. 

<div style="color:red;">
  <span class="Apple-style-span"><b><span class="Apple-style-span" style="font-size:small;">&#8220;BadImageFormatException was unhandled&#8221;</span></b></span>
</div>

<span style="font-size:x-small;"><b><span style="color:red;">Could not load file or assembly &#8216;xxx&#8217;, Version = x.x.x.x, Culture=neutral, PublicKeyToken=null&#8217; or one of its dependencies. An attempt was made to load a program with an incorrent format</span></b></span>

<img height="259" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/b0f0568e1d1b4e3d97071f5966776d72" width="452" /> 

This error is caused by one of the library, i created 1.5 years ago, which is a helper class for crystal report 11 R2 (from VS2005). I am quite worry this library if it is not going to work on any newer version of VS / .NET. Because of different version of .Net Framework!?

Fortunately, I remember that,I have some issue with 64bits windows before with SSIS and on another application that I created. It would be a good try to compile this application in 32 bit.

Here it is my solutions.

1) On Visual Studio Open &#8220;**My Project**&#8221; from the &#8220;**Solution Explorer**&#8220;  
2) Click on the &#8220;**Compile**&#8221; Tab  
3) Then Click on &#8220;**Advanced Compile Options&#8230;**&#8220;  
Select &#8220;**Advanced Compiler Setting**s&#8221; -> Update Target CPU property to &#8220;**x86**&#8221; instead of &#8220;**Any CPU**&#8220;  
<img height="454" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/f3fef2d42b2a46e9bbe720261a8403c2" width="553" /> 

I guess this error occurs is because the library that i created/Compiled is on a 32 bits windows. Now i am using a 64 bits machines. When I run the application i throw that error.

Hope you find it useful.