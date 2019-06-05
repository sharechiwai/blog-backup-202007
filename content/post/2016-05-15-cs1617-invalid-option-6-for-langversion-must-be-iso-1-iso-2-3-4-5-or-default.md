---
id: 3663
title: 'CS1617: Invalid option &#8216;6&#8217; for /langversion; must be ISO-1, ISO-2, 3, 4, 5 or Default'
date: 2016-05-15T00:00:08+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3663
permalink: /2016/05/cs1617-invalid-option-6-for-langversion-must-be-iso-1-iso-2-3-4-5-or-default/
categories:
  - .Net Tips And Tricks
tags:
  - .Net Troubleshooting
  - visual studio
  - Visual Studio 2013
  - Visual Studio 2015
---
在公司**Download** / **執行**網上教學的**Sample Code** 來測試時  
久不久便會出現以下的錯  
&#8220;<span style="color: #ff0000;"><strong>CS1617: Invalid option &#8216;6&#8217; for /langversion; must be ISO-1, ISO-2, 3, 4, 5 or Default</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7528/26841670101_caa6581db3_z.jpg?resize=625%2C182" alt="CS1617: Invalid option '6' for /langversion; must be ISO-1, ISO-2, 3, 4, 5 or Default" width="625" height="182" data-recalc-dims="1" /> 

這是因為Sample Code是用了**Visual Studio 2015** 來建立的 Default的 **.Net Framework**是 **4.5.2** / **4.6**  
而公司是使用**Visual Studio 2013** 的 **.Net Framework是 4.5**

所以<span style="color: #008000;"><strong>Web.Config</strong></span>上有小小Mis-match  
解決方便 十分簡單  
我們只需要更改<span style="color: #3366ff;"><strong> compilerOptions=&#8221;/langversion:6</strong></span> 改變成 <span style="color: #3366ff;"><strong>compilerOptions=&#8221;/langversion:5</strong></span> 便可以了

更改前

<pre>&lt;system.codedom&gt;
 &lt;compilers&gt;
 &lt;compiler language="c#;cs;csharp" extension=".cs" type="Microsoft.CSharp.CSharpCodeProvider,
 System, Version=4.0.0.0, Culture=neutral,
 PublicKeyToken=b77a5c561934e089" warningLevel="4" 
 compilerOptions="/langversion:6 /nowarn:1659;1699;1701"&gt;
 &lt;providerOption name="CompilerVersion" value="v4.0"/&gt;
 &lt;/compiler&gt;
 &lt;compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" type="Microsoft.CodeDom.Providers.DotNetCompilerPlatform.VBCodeProvider, Microsoft.CodeDom.Providers.DotNetCompilerPlatform, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" warningLevel="4" compilerOptions="/langversion:14 /nowarn:41008 /define:_MYTYPE=\&quot;Web\&quot; /optionInfer+"/&gt;
 &lt;/compilers&gt;
 &lt;/system.codedom&gt;</pre>

<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7215/26875879616_b910f4b867_z.jpg?resize=625%2C146" alt="Original Web.config" width="625" height="146" data-recalc-dims="1" />  
更新後

<pre> &lt;system.codedom&gt;
 &lt;compilers&gt;
 &lt;compiler language="c#;cs;csharp" extension=".cs" type="Microsoft.CSharp.CSharpCodeProvider,
 System, Version=4.0.0.0, Culture=neutral,
 PublicKeyToken=b77a5c561934e089" warningLevel="4" 
 compilerOptions="/langversion:5 /nowarn:1659;1699;1701"&gt;
 &lt;providerOption name="CompilerVersion" value="v4.0"/&gt;
 &lt;/compiler&gt;
 &lt;compiler language="vb;vbs;visualbasic;vbscript" extension=".vb" type="Microsoft.CodeDom.Providers.DotNetCompilerPlatform.VBCodeProvider, Microsoft.CodeDom.Providers.DotNetCompilerPlatform, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" warningLevel="4" compilerOptions="/langversion:14 /nowarn:41008 /define:_MYTYPE=\&quot;Web\&quot; /optionInfer+"/&gt;
 &lt;/compilers&gt;
 &lt;/system.codedom&gt;</pre>

<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7093/26841670191_ebdcd69ec8_z.jpg?resize=625%2C214" alt="Web.config for VS2013" width="625" height="214" data-recalc-dims="1" />  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7403/26815596142_9f08f466ff_z.jpg?resize=625%2C297" alt="CS1617 Issue Fixed" width="625" height="297" data-recalc-dims="1" />  
Hope you find it useful