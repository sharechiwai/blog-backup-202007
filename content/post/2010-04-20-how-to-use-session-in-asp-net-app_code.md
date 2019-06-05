---
id: 200
title: How to use Session in ASP.Net App_Code
date: 2010-04-20T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/04/20/how-to-use-session-in-asp-net-app_code
permalink: /2010/04/how-to-use-session-in-asp-net-app_code/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "5361296288156121348"
categories:
  - ASP.Net Tips and Tricks
---
It would be quite useful if we can use &#8220;**Session**&#8221; inside **App_Code in ASP.Net**. E.G. You may not need to pass the &#8220;**Session**&#8221; variable into the Method, You only need to call the **Session(&#8220;Variable Name&#8221;)** inside the method.

However when I try to type the following Code in the vb/cs page which is under **App_Code** folder. It shows the error like this.

**VB.Net**  
<span style="color:#38761d;font-size:x-small;"><b>Dim Var as String = Session(&#8220;VariableName&#8221;)</b></span>

**C#**  
<span style="font-size:x-small;"><b>string var = (string) Session[&#8220;VariableName&#8221;];</b></span>

<span style="color:red;font-size:x-small;"><b>Error: The type or namespace name &#8216;HttpSessionState&#8217; could not be found</b></span>

**Here it is the solutions:**  
To use Session variable inside **App_Code** Folder. 

You need to import a references: Please see the sample code below.

<div style="color:#073763;">
  <span style="font-size:x-small;"><b>VB.Net </b></span>
</div>

<div style="color:#073763;">
  <span style="font-size:x-small;"><b>Import System.Web.SessionState</b></span><span style="font-size:x-small;"><b> </b></span>
</div>

<div style="color:#073763;">
  <span style="font-size:x-small;"><b>C#</b></span>
</div>

<div style="color:#073763;">
  <span style="font-size:x-small;"><b>using System.Web.SessionState;</b></span>
</div>

<div style="color:#073763;">
  <span style="font-size:x-small;"><b><br /></b></span>
</div>

**VB.Net**

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b> Dim ses As  HttpSessionState = HttpContext.Current.Session</b></span>
</div>

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b> Dim VarSession As String = &#8220;&#8221;</b></span>
</div>

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b> If ses(&#8220;VariableName&#8221;) IsNot Nothing Then</b></span>
</div>

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b>     VarSession = DirectCast(ses(&#8220;VariableName&#8221;), String)</b></span>
</div>

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b> End If</b></span>
</div>

**C#**

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b>HttpSessionState ses = HttpContext.Current.Session;</b></span>
</div>

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b>        string VarSession = &#8220;&#8221;;</b></span>
</div>

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b>        if (ses[&#8220;VariableName&#8221;] != null)</b></span>
</div>

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b>        {</b></span>
</div>

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b>            VarSession = (string)ses[&#8220;VariableName&#8221;];</b></span>
</div>

<div style="color:#38761d;">
  <span style="font-size:x-small;"><b>        }</b></span>
</div>

Hope you find it useful.

Happy Coding =).