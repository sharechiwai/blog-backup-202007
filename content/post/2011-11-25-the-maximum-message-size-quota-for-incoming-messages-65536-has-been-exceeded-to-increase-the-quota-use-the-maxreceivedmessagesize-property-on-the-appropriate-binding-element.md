---
id: 1048
title: The maximum message size quota for incoming messages (65536) has been exceeded. To increase the quota, use the MaxReceivedMessageSize property on the appropriate binding element.
date: 2011-11-25T00:00:18+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1048
permalink: /2011/11/the-maximum-message-size-quota-for-incoming-messages-65536-has-been-exceeded-to-increase-the-quota-use-the-maxreceivedmessagesize-property-on-the-appropriate-binding-element/
categories:
  - .Net Tips And Tricks
tags:
  - Web Services
---
今天當試Consume 公司的Partner的 **Web Services**時 出現了以下的錯誤..

&#8220;**<span style="color: #ff0000;">The maximum message size quota for incoming messages (65536) has been exceeded. To increase the quota, use the MaxReceivedMessageSize property on the appropriate binding element.</span>**&#8221;

問題的起因是因為 這個&#8221;**Web Service&#8221;** 回應的**Message** 的大小時大於 65536 [預設的 大小]..  
幸好..這些設定都是可以在開發端的**Web.Config**/**App.Config** 條改

Default的 **Web.Config**/**App.Config**

[xml]  
<binding name="ShareChiWaiHttpBinding" closeTimeout="00:01:00"  
openTimeout="00:01:00" receiveTimeout="00:10:00" sendTimeout="00:01:00"  
allowCookies="false" bypassProxyOnLocal="false" hostNameComparisonMode="StrongWildcard"  
maxBufferSize="65536" maxBufferPoolSize="524288" maxReceivedMessageSize="65536"  
messageEncoding="Text" textEncoding="utf-8" transferMode="Buffered"  
useDefaultWebProxy="true">  
<readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384"  
maxBytesPerRead="4096" maxNameTableCharCount="16384" />  
<security mode="None">  
<transport clientCredentialType="None" proxyCredentialType="None"  
realm="" />  
<message clientCredentialType="UserName" algorithmSuite="Default" />  
</security>  
</binding>  
[/xml]

大家可以看到 預設的  
&#8220;**MaxBufferSize**&#8220;,  &#8220;**maxBufferPoolSize**&#8221; 和 &#8220;**MaxReceivedMessageSize**&#8221; 都是設定為 65536

<pre>maxBufferSize="65536" maxBufferPoolSize="524288" maxReceivedMessageSize="65536"</pre>

**解決方法:  
** 只要把&#8221;**MaxBufferSize**&#8220;,  &#8220;**maxBufferPoolSize**&#8221; 和 &#8220;**MaxReceivedMessageSize**&#8221; 的設定更改為更大的數值.. 如: 5242880 便可以了

**E.G.**

<pre>maxBufferSize="52428800" maxBufferPoolSize="52428800" maxReceivedMessageSize="52428800"</pre>

最後的**Web.config**/**App.config** 就像下面的例子

[xml]  
<binding name="ShareChiWaiHttpBinding" closeTimeout="00:03:00"  
openTimeout="00:03:00" receiveTimeout="00:10:00" sendTimeout="00:03:00"  
allowCookies="false" bypassProxyOnLocal="false" hostNameComparisonMode="StrongWildcard"  
maxBufferSize="52428800" maxBufferPoolSize="52428800" maxReceivedMessageSize="52428800"  
messageEncoding="Text" textEncoding="utf-8" transferMode="Buffered"  
useDefaultWebProxy="true">  
<readerQuotas maxDepth="32" maxStringContentLength="52428800" maxArrayLength="52428800"  
maxBytesPerRead="52428800" maxNameTableCharCount="52428800" />  
<security mode="Transport">  
<transport clientCredentialType="None" proxyCredentialType="None"  
realm="" />  
<message clientCredentialType="UserName" algorithmSuite="Default" />  
</security>  
</binding>  
[/xml]

Hope you find it useful