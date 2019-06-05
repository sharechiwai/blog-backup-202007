---
id: 96
title: Import / using System.IO.Packaging in .Net
date: 2010-06-16T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/06/16/import-using-system-io-packaging-in-net
permalink: /2010/06/import-using-system-io-packaging-in-net/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "7251528879182503814"
categories:
  - .Net Tips And Tricks
---
When I try to import **System.IO.Packaging** onto my windows application. I am not able to find it. However after doing some research online, realise that I need to add the **WindowsBase.dll** reference before I can import the **System.IO.Packaging** namespace.

Here it is the solution:  
1) In the &#8220;Solution Browser&#8221;  
2) Right Click on &#8220;Reference&#8221; ->&#8221;Add Reference..&#8221;  
3) On the &#8220;Add Reference&#8221; windows, click on &#8220;.Net&#8221; tab  
4) Then find.select &#8220;WindowsBase&#8221; on the list below  
5) Click &#8220;Ok&#8221; to add the references.

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/windowsbase.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="340" src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/windowsbase.png?resize=625%2C340" width="625" data-recalc-dims="1" /></a>
</div>

6) You should be able to import **System.IO.Packaging** namespace.  
*however, you cannot import **System.IO.Packaging** namespace in Silverlight Application =( 

Good Luck