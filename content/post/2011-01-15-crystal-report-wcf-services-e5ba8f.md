---
id: 1143
title: Crystal Report WCF Services 序
date: 2011-01-15T00:00:22+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1143
permalink: '/2011/01/crystal-report-wcf-services-%e5%ba%8f/'
categories:
  - .Net Tips And Tricks
  - Crystal Report Tips and Tricks
  - WCF
---
<div id="_mcePaste">
  昨天公司有一個客戶希望我們可以在公司的客戶Portal 上加入一個新的功能&#8230;
</div>

<div id="_mcePaste">
  就是可以樣客戶在我們的Portal上直接Generate一些Report..
</div>

<div id="_mcePaste">
  很可惜公司還未開始使用<strong>Microsoft SQL Server</strong>的<strong>Reporting Services</strong> [<strong>SSRS</strong>]..
</div>

<div id="_mcePaste">
  而是使用<strong>Crystal Report</strong> 來做這個動作的&#8230;
</div>

<div id="_mcePaste">
  但是&#8230;我們又沒有買<strong>Crystal Report Server</strong>來產生Report&#8230;
</div>

<div id="_mcePaste">
  現在的做法是會在我們的電腦上安裝一個<strong>Crystal Report的Runtime</strong>&#8230;
</div>

<div id="_mcePaste">
  去令到所有同事都可以用我們的<strong>In-House Application</strong> 來生產Report&#8230;
</div>

<div id="_mcePaste">
  最後終於想到了解決方法&#8230;
</div>

<div id="_mcePaste">
  就是寫一個WCF 的Service來負責生產Report&#8230;
</div>

<div id="_mcePaste">
  之後再把生產出的的Report Path..
</div>

<div id="_mcePaste">
  發送給Web Portal令到便用者可以Download這個Report&#8230;
</div>

<div id="_mcePaste">
  當我有時間時會整理一下我的筆記&#8230;
</div>

<div id="_mcePaste">
  再和大家分享如何寫一個<strong>WCF Service</strong>來解決這個 <strong>Crystal Report</strong>的問題
</div>

<div id="_mcePaste">
  待續 =)
</div>