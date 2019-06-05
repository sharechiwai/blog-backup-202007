---
id: 358
title: Build a DataTable from Scratch
date: 2009-09-23T09:23:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/09/23/build-a-datatable-from-scratch
permalink: /2009/09/build-a-datatable-from-scratch/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "6629630220323217982"
categories:
  - .Net Tips And Tricks
---
<span class="Apple-style-span" style="border-collapse:separate;color:black;font-family:Arial;font-size:medium;font-style:normal;font-variant:normal;font-weight:normal;letter-spacing:normal;line-height:normal;orphans:2;text-indent:0;text-transform:none;white-space:normal;widows:2;word-spacing:0;"></p> 

<div style="margin:0;">
  My friend has asked my how to build a data table manually. E.g. Add a custom rows into the data table &#8230;etc.
</div>

<div style="margin:0;">
  Here it is an example to build a data table from scratch. in C#
</div>

<div style="margin:0;">
  <i>using System.Data;</i>
</div>

<div style="margin:0;">
  //First of all you need to create a new table<br /><span style="font-size:x-small;"><i>DataTable tbl = new DataTable();</i></span>
</div>

<div style="margin:0;">
  //then you need to specific the columns that you want to have on that DataTable
</div>

<div style="margin:0;">
  <span style="font-size:x-small;"><i>tbl.Columns.Add[&#8220;Column1&#8221;];<br />tbl.Columns.Add[&#8220;Column2&#8221;];<br />tbl.Columns.Add[&#8220;Column3&#8221;];</i></span><br />//&#8230;ETC.
</div>

<div style="margin:0;">
  //Then you can start to build your table.<br />//You need to create a empty row and then put it into the data table<br /><span style="font-size:x-small;"><i>DataRow dr = new DataRow();</i></span>
</div>

<div style="color:#38761d;margin:0;">
  <span style="font-size:x-small;"><i>dr[&#8220;Column1&#8221;].Add(&#8220;Hello&#8221;);</i><br /><i>dr[&#8220;Column2&#8221;].Add(&#8220;MyTable&#8221;);<br />dr[&#8220;Column1&#8221;].Add(&#8220;Example&#8221;);</i></span>
</div>

<div style="color:#38761d;margin:0;">
  <span style="font-size:x-small;">//Finally add it into the data table<br /><i>tbl.Rows.Add(dr);</i></span>
</div>

<div style="margin:0;">
  There it is you just created a Data table with 1 row.
</div>

<div style="margin:0;">
  Happy programming
</div>

<p>
  </span>
</p>