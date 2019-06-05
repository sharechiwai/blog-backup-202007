---
id: 3425
title: 'MSSQL How to convert timestamp yyyyMMddhhmmss to DateTime format &#8211; 如何把 TimeStamp yyyyMMddhhmmss 轉成 日期時間yyyy-MM-dd hh:mm:ss'
date: 2015-06-03T00:00:13+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3425
permalink: '/2015/06/mssql-how-to-convert-timestamp-yyyymmddhhmmss-to-datetime-format-%e5%a6%82%e4%bd%95%e6%8a%8a-timestamp-yyyymmddhhmmss-%e8%bd%89%e6%88%90-%e6%97%a5%e6%9c%9f%e6%99%82%e9%96%93yyyy-mm-dd-hhmmss/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TimeStamp
  - TSQL function
---
今日同事又有一個有趣的問題&#8230;  
就是如何把 **TimeStamp** **yyyyMMddhhmmss**轉成 日期時間**yyyy-MM-dd hh:mm:ss** 呢  
來把現在的日期時間轉

之前的網誌常常和大家介紹如何用不同的 programming language 轉為 **Timestamp** **yyyyMMddhhmmss**  
e.g. **20150603012345  
<a href="http://blog.sharechiwai.com/2010/11/generate-timestamp-yyyymmddhhmmssin-mssql-2/" target="_blank">Generate Timestamp (yyyyMMddhhmmss)in MSSQL — 在MSSQL 中建立一個像時間戳的值</a>  
** 

做了一會research 之後發現  
我們可以使用<span style="color: #008000;"><strong>STUFF</strong></span> 這個功能去分數這些數字..之後再把他們轉換為日期時間

我在建立一個 function 方便大家轉換 **Timestamp** 到日期時間格式  
**解決方法**

<pre>GO
-- =============================================
-- Author:		 sharechiwai
-- Create date: 2015-06-03
-- Description:	 This function used to convert timestamp yyyyMMddhhmmss to DateTime format
-- =============================================
CREATE FUNCTION [dbo].[ConvertTimestampToDateTime]
(
	-- Add the parameters for the function here
	@TimeStamp VARCHAR(14)=''
)
RETURNS DateTime
AS
BEGIN	
	-- Return the result of the function
	RETURN CAST(STUFF(STUFF(STUFF(@TimeStamp, 9, 0, ' '), 12, 0, ':'), 15, 0, ':') AS DATETIME)
END
GO

</pre>

<img class="alignnone" src="https://i0.wp.com/farm1.static.flickr.com/419/18384493871_71eb86161b_z.jpg?resize=625%2C263" alt="TSQL Convert TimeStamp to DateTime function" width="625" height="263" data-recalc-dims="1" /> 

**使用方法**

<pre>SELECT dbo.ConvertTimestampToDateTime('20150603012345')
</pre>

<img class="alignnone" src="https://i0.wp.com/farm8.static.flickr.com/7786/18378806322_c5d24b93fc_z.jpg?resize=481%2C243" alt="TSQL Convert TimeStamp to DateTime Format function usage" width="481" height="243" data-recalc-dims="1" /> 

Hope you find it useful