---
id: 179
title: 'CA2000 : Microsoft.Reliability : In method &#8216;xxx&#8217;, call System.IDisposable.Dispose on object &#8216;XXX&#8217;'
date: 2010-04-26T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/04/26/ca2000-microsoft-reliability-in-method-xxx-call-system-idisposable-dispose-on-object-xxx
permalink: /2010/04/ca2000-microsoft-reliability-in-method-xxx-call-system-idisposable-dispose-on-object-xxx/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4944611103449701456"
categories:
  - .Net Tips And Tricks
---
When I try to compile my .Net application I have received the warning below:  
<span style="color:red;font-size:x-small;"><strong>&#8220;CA2000 : Microsoft.Reliability : In method &#8216;GetResponse&#8217;, call System.IDisposable.Dispose on object &#8216;XXX&#8217; </strong></span><span style="font-size:x-small;"><strong><span style="color:red;">before all references to it are out of scope.</span></strong></span><span style="color:red;font-size:x-small;"><strong>&#8220;</strong></span>

When I look up this warning on **Microsoft MSDN**, it said, it is caused by &#8220;<span style="font-size:x-small;"><strong>A local object of a System.IDisposable  type is created but the object is not disposed before all references to the object are out of scope.</strong><span style="color:blue;"> </span></span>&#8221;

Althought it is just a warning, I guess it would could improve the efficient/performance a bit, if I do what it said. At the end, I used the &#8220;**Using Statement**&#8221; [in VB.net] to wrap objects inside that method, and the warning has gone.

**Here it is my sample code:**

<span style="color:#38761d;font-size:x-small;"><strong>Public Function GetResponse as ShareObject<br /> Dim MyHelperInfo As New MyHelperClass</strong></span>

 **<span style="color:#008000;">Dim response As ShareResponse<br /> Using MyHelperInfo<br /> Dim WebServiceShareChiWai As New WebServiceShareChiWaiRequest<br /> WebServiceShareChiWai.Param1 = &#8220;SharechiwaiVariable&#8221;<br /> response = MyHelperInfo.SendRequest(WebServiceShareChiWai)<br /> End Using<br /> Return response.ShareObject</span>**

<span style="color:#008000;"><strong>End Function</strong></span>

Hope you find it useful.

Happy coding =)