---
id: 156
title: 'The type or namespace name &#8216;DataContractJsonSerializer&#8217; could not be found (are you missing a using directive or an assembly reference?)'
date: 2010-05-05T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/05/05/the-type-or-namespace-name-datacontractjsonserializer-could-not-be-found-are-you-missing-a-using-directive-or-an-assembly-reference
permalink: /2010/05/the-type-or-namespace-name-datacontractjsonserializer-could-not-be-found-are-you-missing-a-using-directive-or-an-assembly-reference/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "6245102178414155368"
categories:
  - .Net Tips And Tricks
  - Silverlight Tips and Tricks
---
When I try to upgrade my application, which I created from **Silverlight2** to **Silverlight4**.  
I have received the following error.

&#8220;**The type or namespace name &#8216;DataContractJsonSerializer&#8217; could not be found (are you missing a using directive or an assembly reference?)** &#8220;  
I have spent ages, try to figure out which assembly refernce I have missed in order to get it work.  
E.g. I have checked that I have got the following reference added to the application.  
**<span style="color:#38761d;">System.Runtime.Serialization;</span><br style="color:#38761d;" /><span style="color:#38761d;">System.Runtime.Serialization.Json;</span>**

Finally, I remembered which reference I am missing.

Here it is the assembly reference you need to import, when you receive error message about  
&#8220;<span style="color:red;font-size:x-small;"><b>The type or namespace name &#8216;DataContractJsonSerializer&#8217; could not be found (are you missing a using directive or an assembly reference?) </b></span>&#8220;  
**System.ServiceModel.Web**

1) Right click on your &#8220;**Project**&#8221; and select &#8220;**Add Reference&#8230;**&#8220;  
2) On the &#8220;**.Net**&#8221; tab  
3) Select &#8220;**System.ServiceModel.Web**&#8221; and Click &#8220;**OK**&#8220;  
<span id="goog_1928402799"></span><span id="goog_1928402800"></span>

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/addservicemodelweb.jpg" style="margin-left:1em;margin-right:1em;"><img border="0" height="269" src="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/addservicemodelweb.jpg?resize=320%2C269" width="320" data-recalc-dims="1" /></a>
</div>

This error should be fixed.

Hope you find it useful.