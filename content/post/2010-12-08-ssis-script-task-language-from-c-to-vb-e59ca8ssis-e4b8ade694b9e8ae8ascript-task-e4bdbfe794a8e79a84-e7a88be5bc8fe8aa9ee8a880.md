---
id: 1092
title: 'SSIS Script Task language From C# to VB &#8212; 在SSIS 中改變Script Task 使用的 程式語言'
date: 2010-12-08T00:00:55+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1092
permalink: '/2010/12/ssis-script-task-language-from-c-to-vb-%e5%9c%a8ssis-%e4%b8%ad%e6%94%b9%e8%ae%8ascript-task-%e4%bd%bf%e7%94%a8%e7%9a%84-%e7%a8%8b%e5%bc%8f%e8%aa%9e%e8%a8%80/'
categories:
  - .Net Tips And Tricks
  - MSSQL Tips and Tricks
  - SSIS
---
<div id="_mcePaste">
  今日公司有個朋友問&#8230;
</div>

<div id="_mcePaste">
  為什麼你的<strong>SSIS Script Task</strong> 元件只可以用<strong>C#</strong> 來寫程式碼的?
</div>

<div id="_mcePaste">
  我記得好像有地方可以修改的&#8230;
</div>

<div id="_mcePaste">
  最後在自己的電腦上嘗試了建立一個<strong>SSIS Script Task</strong> 的 <strong>Package</strong>
</div>

<div id="_mcePaste">
  原來要改變用<strong>VB </strong>或<strong>C#</strong> 來寫這個<strong>Script Task</strong> 是十分簡單的
</div>

<div id="_mcePaste">
  只要在<strong>Script Langange</strong> 選項上更變便可<br /> <a href="https://i1.wp.com/farm6.static.flickr.com/5108/5688319182_d2c2e02efa.jpg"><img class="alignnone size-full wp-image-1093" title="ScriptTask" src="https://i1.wp.com/farm6.static.flickr.com/5108/5688319182_d2c2e02efa.jpg?w=625" alt="" data-recalc-dims="1" /></a>
</div>

<div id="_mcePaste">
  但是一旦選擇了便沒有很再改變了
</div>

<div id="_mcePaste">
  Hope you find it useful
</div>