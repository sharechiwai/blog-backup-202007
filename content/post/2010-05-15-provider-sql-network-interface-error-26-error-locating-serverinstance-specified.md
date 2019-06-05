---
id: 132
title: 'Provider: SQL Network Interface, error: 26 &#8211; Error Locating Server/Instance Specified'
date: 2010-05-15T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/05/15/provider-sql-network-interface-error-26-error-locating-serverinstance-specified
permalink: /2010/05/provider-sql-network-interface-error-26-error-locating-serverinstance-specified/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "7853689376991828504"
categories:
  - MSSQL Tips and Tricks
---
After re-install **Microsoft SQL Server**, when I try to connect to the **SQL Server**, I have received the error below.  
&#8220;<span style="color:#ff0000;"><strong>A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (Provider: SQL Network Interface, error: 26 &#8211; Error Locating Server/Instance Specified</strong></span>&#8221;

<div class="separator" style="clear:both;text-align:center;">
  <a style="margin-left:1em;margin-right:1em;" href="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/r2cannotconnect.jpg"><img src="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/r2cannotconnect.jpg?resize=400%2C126" border="0" alt="" width="400" height="126" data-recalc-dims="1" /></a>
</div>

When I try to connect it has already fill in the &#8220;**Server name**&#8221; for me, so I assume that is the one. However as from the error message it said &#8220;The server was not found or was not accessible&#8221;, so I try my computer can find any SQL Server. I find out that I do no need to put the instance name on to the &#8220;**Server name:**&#8221; section. E.g. I only need to put the name of the server on the &#8220;**Server name:**&#8221; text box and it works.

If you want to discover if there any **SQL** server that you can connect you can try to following.  
In the &#8220;**Connect to Server**&#8221; Windows

<div class="separator" style="clear:both;text-align:center;">
  <a style="margin-left:1em;margin-right:1em;" href="http://sharechiwai.files.wordpress.com/2010/05/connecttoserver.jpg"><img src="http://sharechiwai.files.wordpress.com/2010/05/connecttoserver.jpg?w=300&#038;resize=400%2C298" border="0" alt="" width="400" height="298" data-recalc-dims="1" /></a>
</div>

Click on the drop down list beside the &#8220;**Server Name:**&#8221;  
And click on &#8220;Browse&#8221;

Then you should be able see the &#8220;**Browse for Servers&#8221;** windows.

<div class="separator" style="clear:both;text-align:center;">
  <a style="margin-left:1em;margin-right:1em;" href="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/browseforserver.jpg"><img src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/browseforserver.jpg?resize=400%2C396" border="0" alt="" width="400" height="396" data-recalc-dims="1" /></a>
</div>

You can then click on the &#8220;**+**&#8221; beside &#8220;**Database Engine**&#8221; the see if there SQL Server exist on your local machine, or you can click on the &#8220;**Network Servers**&#8221; tab to get a list of SQL server which you can connect over the network.

Hope yu find it useful.