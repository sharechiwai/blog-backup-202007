---
id: 368
title: Call javascript method from asp.net code behind
date: 2009-09-12T09:12:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/12/call-javascript-method-from-asp-net-code-behind
permalink: /2009/09/call-javascript-method-from-asp-net-code-behind/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4022190638585617185"
categories:
  - .Net Tips And Tricks
  - ASP.Net Tips and Tricks
---
<span style="font-family:verdana;">Sometime I found it more efficient to run JavaScript on asp.net rather than doing everything on VB/c#.</span>

<span style="font-family:verdana;">Hope do you call a JavaScript by using the code behind aspx?</span>

<span style="font-family:verdana;">You can use the following code</span>

<span style="font-family:verdana;">Page.ClientScript.RegisterStartupScript(Me.GetType, &#8220;Key name&#8221;, &#8220;Javascript that you would like to use&#8221;, &#8216;Add script tag)</span>

<span style="font-family:verdana;">Here it is an example (&#8220;Hello OurChiWai&#8221;)</span>

<span style="font-family:verdana;">VB.net</span>  
<span style="font-weight:bold;color:rgb(0,153,0);font-size:85%;"><span style="font-family:verdana;">Page.ClientScript.RegisterStartupScript(Me.GetType, &#8220;MyJS&#8221;, &#8220;alert(&#8216;Hello OurChiWai&#8217;);&#8221;, true)</span></span>

<span style="font-family:verdana;">C#</span>  
<span style="font-weight:bold;color:rgb(0,153,0);font-size:85%;"><span style="font-family:verdana;">Page.ClientScript.RegisterStartupScript(this.GetType, &#8220;MyJS&#8221;, &#8220;alert(&#8216;Hello OurChiWai&#8217;);&#8221;, true);</span></span>

<span style="font-family:verdana;">&#8216;I called my Key &#8220;MyJS&#8221;</span>  
<span style="font-family:verdana;">The JavaScript that I am going to run is to do a message box which shows &#8220;Hello OurChiWai&#8221;</span>

<span style="font-family:verdana;">Happy coding.</span>