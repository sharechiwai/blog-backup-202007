---
id: 2510
title: 'Show table fragmentation on TSQL &#8211; 如何顯示 MSSQL Table 上有沒有碎片呢?'
date: 2012-08-02T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2510
permalink: '/2012/08/show-table-fragmentation-on-tsql-%e5%a6%82%e4%bd%95%e9%a1%af%e7%a4%ba-mssql-table-%e4%b8%8a%e6%9c%89%e6%b2%92%e6%9c%89%e7%a2%8e%e7%89%87%e5%91%a2/'
categories:
  - MSSQL Tips and Tricks
tags:
  - TSQL
---
上週老闆希望把我負責的程式更新多一些**Summary** 的功能..  
其實這一個程式已經很久沒有更新了&#8230; [大概兩年多]  
所以回看這一個程式..感覺到自己當時的技術有幾差

今次要增加的功能很多都是和**Database**有關的..  
為了提高效能..  
所以都想學習多一些多**Database Maintenance** **資料庫維護**  
和看看怎樣可以提升**Query的速度和效能**&#8230;  
首先..當然是要看看將會使用到的Table 上的**資料data**/和**表Table**上的**碎片**有幾分散..  
如果分散得大的話使要進行**Index Rebuild** 了  
有興趣的朋友可以參考以下的網誌

# <a title="Permalink to TSQL Defrag index in a table –  MSSQL重建資料表的索引" href="http://blog.sharechiwai.com/2012/08/tsql-defrag-index-in-a-table-mssql%e9%87%8d%e5%bb%ba%e8%b3%87%e6%96%99%e8%a1%a8%e7%9a%84%e7%b4%a2%e5%bc%95/" rel="bookmark">TSQL Defrag index in a table – MSSQL重建資料表的索引 </a>

今天想和大家介紹一個有用的SQL Command  
就是用來**查看資料庫上的Table/表上的資料和Index索引的碎片資料**的..  
大家可以使用以下的Command

[sql]  
DBCC SHOWCONTIG ("Table name");

&#8211;E.G.  
DBCC SHOWCONTIG (ShareChiWai_SampleTable);  
[/sql]

**之後便會出現和下面相似的結果**  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/7c32a640b1d140ba9cacdbe8cdb922bd" alt="DBCC SHOWCONTIG result" width="712" height="278" />  
**DBCC SHOWCONTIG scanning &#8216;ShareChiWai_SampleTable&#8217; table&#8230;**  
 **Table: &#8216;ShareChiWai_SampleTable&#8217; (43147199); index ID: 1, database ID: 5**  
 **TABLE level scan performed.**  
 **&#8211; Pages Scanned&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;..: 41**  
 **&#8211; Extents Scanned&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;: 11**  
 **&#8211; Extent Switches&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;: 10**  
 **&#8211; Avg. Pages per Extent&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;: 3.7**  
 **&#8211; Scan Density [Best Count:Actual Count]&#8230;&#8230;.: 54.55% [6:11]**  
 **&#8211; Logical Scan Fragmentation &#8230;&#8230;&#8230;&#8230;&#8230;&#8230;: 17.07%**  
 **&#8211; Extent Scan Fragmentation &#8230;&#8230;&#8230;&#8230;&#8230;&#8230;.: 54.55%**  
 **&#8211; Avg. Bytes Free per Page&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;: 92.5**  
 **&#8211; Avg. Page Density (full)&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;&#8230;: 98.86%**  
 **DBCC execution completed. If DBCC printed error messages, contact your system administrator.**

**以下是這些結果的意思**

<table>
  <tr>
    <th>
      Statistic
    </th>
    
    <th>
      Description
    </th>
  </tr>
  
  <tr>
    <td>
      <strong>Pages Scanned</strong>
    </td>
    
    <td>
      Number of pages in the table or index.<br /> 資料表或索引中的頁數。
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Extents Scanned</strong>
    </td>
    
    <td>
      Number of extents in the table or index.<br /> 資料表或索引中的範圍數目。
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Extent Switches</strong>
    </td>
    
    <td>
      Number of times the DBCC statement moved from one extent to another while the statement traversed the pages of the table or index.<br /> 當 DBCC 陳述式往返資料表或索引頁面時，在各範圍之間的移動次數。
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Avg. Pages per Extent</strong>
    </td>
    
    <td>
      Number of pages per extent in the page chain.<br /> 在頁面鏈結中，每個範圍的頁數。
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Scan Density [Best Count: Actual Count]</strong>
    </td>
    
    <td>
      Is a percentage. It is the ratio <strong>Best Count</strong> to <strong>Actual Count</strong>. This value is 100 if everything is contiguous; if this value is less than 100, some fragmentation exists.<br /> 這是一個百分比。 它是<strong>最佳次數</strong>與<strong>實際次數</strong>的比例。 如果每個項目都是連續的，這個值就是 100；如果這個值小於 100，就會有某些片段存在。<strong>Best Count</strong> is the ideal number of extent changes if everything is contiguously linked. <strong>Actual Count</strong> is the actual number of extent changes.<br /> <strong>最佳次數</strong>是每個項目都連續連結時，理想的範圍變更數目。 <strong>實際次數</strong>是實際的範圍變更數目。
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Logical Scan Fragmentation</strong>
    </td>
    
    <td>
      Percentage of out-of-order pages returned from scanning the leaf pages of an index. This number is not relevant to heaps. An out-of-order page is a page for which the next physical page allocated to the index is not the page pointed to by the next-page pointer in the current leaf page.<br /> 掃描索引分葉頁時所傳回失序頁面的百分比。 這個數字與堆積無關。 失序頁面是指配置給索引之下一個實體頁面的頁面，並不是目前分葉頁中下一頁指標所指向的頁面。
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Extent Scan Fragmentation</strong>
    </td>
    
    <td>
      Percentage of out-of-order extents in scanning the leaf pages of an index. This number is not relevant to heaps. An out-of-order extent is one for which the extent that contains the current page for an index is not physically the next extent after the extent that contains the previous page for an index.<br /> 掃描索引分葉頁時之失序範圍的百分比。 這個數字與堆積無關。 失序範圍是索引目前頁面所在之範圍，實際上不是索引上一頁所在範圍之下一範圍的範圍。
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Avg. Bytes Free per Page</strong>
    </td>
    
    <td>
      Average number of free bytes on the pages scanned. The larger the number, the less full the pages are. Lower numbers are better if the index will not have many random inserts. This number is also affected by row size; a large row size can cause a larger number.<br /> 掃描頁面的平均可用位元組數。 數目愈大，頁面的飽和度愈低。 如果索引沒有許多隨機的插入，數目低會比較好。 這個數目也受到資料列大小的影響；資料列愈大，這個數目也愈大。
    </td>
  </tr>
  
  <tr>
    <td>
      <strong>Avg. Page density (full)</strong>
    </td>
    
    <td>
      Average page density, as a percentage. This value takes into account row size. Therefore, the value is a more accurate indication of how full your pages are. The larger the percentage, the better.<br /> 平均頁面密度，這是一個百分比。 這個值將資料列大小考慮在內。 因此，這個值是更精確的頁面飽和度指示。 百分比愈大，愈好
    </td>
  </tr>
</table>

**詳情可以參考以下URL**  
<http://msdn.microsoft.com/zh-tw/library/ms175008.aspx>

Hope you find it useful