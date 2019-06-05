---
id: 296
title: How to Install SQL2000 on Win7
date: 2010-02-22T02:20:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/02/22/how-to-install-sql2000-on-win7
permalink: /2010/02/how-to-install-sql2000-on-win7/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "2412229205705676913"
categories:
  - MSSQL Tips and Tricks
---
<div class="" style="clear:both;text-align:left;">
  Finally, I have rebuilt the computer at work and put Win7 64bit on. It is a decent computer, I started to use it last April and it run XP64bit. Unfortunately, it does not work properly, the printer driver did not work properly[it always has network problem, e.g. drop SQL connection randomly], which lost the purpose of having that powerful computer&#8230;
</div>

<div class="" style="clear:both;text-align:left;">
  After installed the Win7, I would need to install all other software that I use, the first software I can think of is SQL2000 Enterprise Manager [It is a good tools for you to do simple query/ edit data and tables].  
</div>

<div class="" style="clear:both;text-align:left;">
  When I try to install SQL2000 on Windows7 by using <b>auto-run</b>, it did not let me, because of the compatibility problem. 
</div>

<div class="separator" style="clear:both;text-align:left;">
   <a href="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/32bit64bitversionnotcompatible.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="107" src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/32bit64bitversionnotcompatible.png?resize=400%2C107" width="400" data-recalc-dims="1" /></a>
</div>

<div class="separator" style="clear:both;text-align:left;">
</div>

<div class="separator" style="clear:both;text-align:left;">
  I try to find a solution online, however, I found a link on Microsoft, they said SQL2000 will not work on Win7/SQL2008&#8230;Then I try to work around this problem.
</div>

<div class="separator" style="clear:both;text-align:left;">
</div>

Here it is work around:  
1) On the CD/DVD drive Click on &#8220;**Open**&#8220;, you will then see the content of the disk

<div class="separator" style="clear:both;text-align:center;">
  <a href="http://sharechiwai.files.wordpress.com/2010/02/browsesql2000cdsetupbat.png" style="clear:left;float:left;margin-bottom:1em;margin-right:1em;"><img border="0" height="206" src="http://sharechiwai.files.wordpress.com/2010/02/browsesql2000cdsetupbat.png?w=300&#038;resize=400%2C206" width="400" data-recalc-dims="1" /></a>
</div>



<div class="separator" style="clear:both;text-align:left;">
</div>

2) find a file called &#8220;**setup.bat**&#8220;  
3) double click on it, you will see the pop-up warning about &#8220;**Program Compatibility**&#8220;

<div class="separator" style="clear:both;text-align:center;">
  <a href="http://sharechiwai.files.wordpress.com/2010/02/sql2000warning.png" style="clear:left;float:left;margin-bottom:1em;margin-right:1em;"><img border="0" height="187" src="http://sharechiwai.files.wordpress.com/2010/02/sql2000warning.png?w=300&#038;resize=400%2C187" width="400" data-recalc-dims="1" /></a>
</div>



<div class="separator" style="clear:both;text-align:left;">
  4) Click on &#8220;<b>Run Program</b>&#8220;
</div>

<div class="separator" style="clear:both;text-align:left;">
  5) Then another pop-up appear explain 
</div>

<div class="separator" style="clear:both;text-align:left;">
  <span style="font-size:x-small;">&#8220;<b>Microsoft SQL Server 2000 Standard Edition server component is not supported on this operating system. Onlu client components will be available for installation</b>.&#8221; [which is fine for me.]</span>
</div>

<div class="separator" style="clear:both;text-align:left;">
</div>

<a href="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/sql2000support.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="152" src="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/sql2000support.png?resize=400%2C152" width="400" data-recalc-dims="1" /></a>

<div class="separator" style="clear:both;text-align:left;">
  6) Then the installation screen appear.
</div>

<div class="separator" style="clear:both;text-align:left;">
   <a href="https://i0.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/sql2000setup.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="285" src="https://i0.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/sql2000setup.png?resize=400%2C285" width="400" data-recalc-dims="1" /></a>
</div>

<div class="separator" style="clear:both;text-align:left;">
  7) You can then carry on to install SQL Server 2000 by following the on screen steps.
</div>

<div class="separator" style="clear:both;text-align:left;">
</div>

<div class="separator" style="clear:both;color:red;text-align:left;">
  <b>Another work around, [which I have not try properly is]</b>
</div>

<div class="separator" style="clear:both;text-align:left;">
</div>

<div class="separator" style="clear:both;text-align:left;">
  1) Right click on the CD/DVD drive and select &#8220;<b>Troubleshoot compatibilty</b>&#8220;
</div>

<div class="separator" style="clear:both;text-align:left;">
</div>

<div class="separator" style="clear:both;text-align:center;">
  <a href="http://sharechiwai.files.wordpress.com/2010/02/troubleshootcompatibility.png" style="clear:left;float:left;margin-bottom:1em;margin-right:1em;"><img border="0" src="http://sharechiwai.files.wordpress.com/2010/02/troubleshootcompatibility.png?w=625" data-recalc-dims="1" /></a>
</div>

<div class="separator" style="clear:both;text-align:center;">
</div>

<div class="separator" style="clear:both;text-align:center;">
</div>

<div class="separator" style="clear:both;text-align:left;">
  2) The &#8220;<b>Program Compatibility</b>&#8221; dialog will appeal
</div>

<div class="separator" style="clear:both;text-align:center;">
</div>

<div class="separator" style="clear:both;text-align:center;">
</div>

<a href="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/programcompatibility.png" style="clear:left;float:left;margin-bottom:1em;margin-right:1em;"><img border="0" src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/programcompatibility.png?w=625" data-recalc-dims="1" /></a>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
</div>

<div style="text-align:left;">
  3) Then select &#8220;<b>Try recommended setting</b>&#8221; and follow the instruction -> you may need to restart after apply for the settings.
</div>

<div class="separator" style="clear:both;text-align:center;">
  <a href="http://oldblog.sharechiwai.com/wp-content/uploads/2010/08/programcompatibility.png" style="clear:left;float:left;margin-bottom:1em;margin-right:1em;"></a><a href="https://i0.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/recommentedcompatibility2.png" style="clear:left;float:left;margin-bottom:1em;margin-right:1em;"><img border="0" src="https://i0.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/recommentedcompatibility2.png?w=625" data-recalc-dims="1" /></a>
</div>

I would be grateful, you can you let me know whether this could help you install SQL2000 in your version of Win7 too.

Hope you found it useful!!!  
Good luck =)