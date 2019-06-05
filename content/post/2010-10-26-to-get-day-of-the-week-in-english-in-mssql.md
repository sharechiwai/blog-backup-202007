---
id: 59
title: 'To get Day of the week in English in MSSQL &#8212;在MSSQL 中找出今日或某一個日子是那一個星期天'
date: 2010-10-26T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2011/05/09/to-get-day-of-the-week-in-english-in-mssql
permalink: /2010/10/to-get-day-of-the-week-in-english-in-mssql/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "8921129761568097891"
categories:
  - MSSQL Tips and Tricks
---
<span class="Apple-style-span" style="font-family: 'Times New Roman'; font-size: 16px;"><span class="Apple-style-span" style="font-size: small;"><span class="Apple-style-span" style="font-size: 13px;">公司上的一個網上應用程式有一個功能是要把資料作統計..<br /> 是分別把每個月的數據分開入 不同星期 E.G. 星期一至星期六<br /> 之後出一個<strong>Bar Chart</strong>&#8230;<br /> 由於所有數據都是在數據庫中..<br /> 所以最理想的方法當然是使用SQL 來把日子分類成<br /> 星期一至星期日..<br /> 在了一會兒Research 之後終於找到了我需要用的 SQL Code 了</span></span></span>

<span class="Apple-style-span" style="font-family: 'Times New Roman'; font-size: 16px;"><span class="Apple-style-span" style="font-size: small;"><span class="Apple-style-span" style="font-size: 13px;">我們可以用SQL 中的 DATENAME 功能來實現這個效果<br /> E.G.</span></span> <span style="color: #008000;"><strong>SELECT DATENAME(dw,6)</strong></span><br /> 會出現 &#8220;星期日&#8221;<br /> </span>  
<span class="Apple-style-span" style="font-family: 'Times New Roman'; font-size: 16px;">這是因為 數字是由0開始的<br /> 而我的資料庫Language 設定是 us_english<br /> 所以會以星期一為每週開始的第一日 而星期日會是每週的最後一日<br /> 有些Language 會設定星期日</span>每週開始的第一日  
而星期六會是每週的最後一日

<span class="Apple-style-span" style="font-family: 'Times New Roman'; font-size: 16px;">所以大家可能要小心一點</p> 

<p>
  </span>最後我把我的SQL 寫成<br /> <span style="color: #008000;">SELECT DATENAME(dw,StartTime), COUNT(*) AS NoOfRecord<br /> FROM table1<br /> GROUP BY DATENAME(dw,StartTime)<br /> ORDER BY DATENAME(dw,StartTime)</span>
</p>

<p>
  Hope you find it useful
</p>