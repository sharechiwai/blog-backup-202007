---
id: 360
title: 'The log file for database &#8216;XXX&#8217; is full. Back up the transaction log for the database to free up some log space.'
date: 2009-09-20T09:20:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/20/the-log-file-for-database-xxx-is-full-back-up-the-transaction-log-for-the-database-to-free-up-some-log-space
permalink: /2009/09/the-log-file-for-database-xxx-is-full-back-up-the-transaction-log-for-the-database-to-free-up-some-log-space/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4548561188476878729"
categories:
  - MSSQL Tips and Tricks
---
<span class="Apple-style-span" style="font-family:Verdana;font-size:13px;"></p> 

<div style="margin-top:0;margin-bottom:0;">
  When I try to update some data on the database today, I have received the following error.
</div>

<div style="margin-top:0;margin-bottom:0;">
  &#8220;<span class="Apple-style-span" style="color:#FF0000;"><b><span class="Apple-style-span" style="font-size:small;">The log file for database &#8216;XXX&#8217; is full. Back up the transaction log for the database to free up some log space.</span></b></span>&#8220;
</div>

<div style="margin-top:0;margin-bottom:0;">
</div>

<div style="margin-top:0;margin-bottom:0;">
  It said the log file for the database is full, so I need to clear the log to free up some space.
</div>

<div style="margin-top:0;margin-bottom:0;">
  Fortunatley, it is quite easy to do. What you need to do is as the following:
</div>

<div style="margin-top:0;margin-bottom:0;">
  Solution:
</div>

<div style="margin-top:0;margin-bottom:0;">
  1) Open up <b>SQL Server Management Studio</b>/ <b>SQL Query Analyzer </b>
</div>

<div style="margin-top:0;margin-bottom:0;">
  2) Select the database which you want to to clear the transaction log.
</div>

<div style="margin-top:0;margin-bottom:0;">
  3) the run the query below.<br /><b><span class="Apple-style-span" style="color:#006600;"><span class="Apple-style-span" style="font-size:small;">BACKUP LOG [<span class="Apple-style-span" style="color:#330099;">DatabaseName</span>] WITH TRUNCATE_ONLY<br />DBCC SHRINKFILE ([<span class="Apple-style-span" style="color:#330099;">DatabaseLogName_Log</span>],500)</span></span></b></p>
</div>

<div style="margin-top:0;margin-bottom:0;">
  Hope you find it useful.
</div>

<p>
  </span>
</p>