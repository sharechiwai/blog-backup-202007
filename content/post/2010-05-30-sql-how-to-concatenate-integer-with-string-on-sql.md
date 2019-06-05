---
id: 65
title: SQL How to concatenate Integer with string on SQL
date: 2010-05-30T03:28:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/09/30/sql-how-to-concatenate-integer-with-string-on-sql
permalink: /2010/05/sql-how-to-concatenate-integer-with-string-on-sql/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "6694836090828697487"
categories:
  - MSSQL Tips and Tricks
---
今日有朋友問我一個SQL問題  
就是如何打數字 和Varchar合併在一起..  
E.G.  
我個有一個Varchar =&#8217;2011&#8242;  
和一個數字20  
DECLARE @VarcharText VARCHAR(10) = &#8216;2011&#8217;  
DECLARE @InvValue INT = 12  
當你寫 執行  
SELECT &#8220;2011&#8221; + @InvValue

<div style="margin: 0;">
</div>

<div style="margin: 0;">
  use CAST( as VARCHAR(10))
</div>

<div style="margin: 0;">
  My friend has asked me a simple SQL question. which is: How to
</div>