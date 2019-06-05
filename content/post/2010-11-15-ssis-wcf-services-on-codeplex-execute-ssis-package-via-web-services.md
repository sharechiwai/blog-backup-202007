---
id: 955
title: 'SSIS WCF Services on CodePlex &#8212; Execute SSIS Package Via Web Services'
date: 2010-11-15T00:00:11+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=955
permalink: /2010/11/ssis-wcf-services-on-codeplex-execute-ssis-package-via-web-services/
categories:
  - .Net Tips And Tricks
  - ShareChiWaiLib
  - SSIS
  - SSISServices
  - WCF
  - Web Services
---
<div id="_mcePaste">
  今日終於在<strong>CodePlex </strong>上和大家分享了我第二個Project了
</div>

<div id="_mcePaste">
  這個Project 是一個WCF Service, 如果執行 <strong>SQL Server Integration Services</strong> [<strong>SSIS</strong>] 的&#8230;
</div>

<div id="_mcePaste">
  在大概一年多前才剛剛在朋友身上學會了使用 <strong>Data Transformation Services</strong> [<strong>DTS</strong>]
</div>

<div id="_mcePaste">
  一個在<strong>SQL Server 2000</strong> 或之前版本的 <strong>SQL </strong>功能
</div>

<div id="_mcePaste">
  令我們可以寫一些<strong>DTS Package</strong> 之後在自己寫的<strong>.Net Application</strong> 上執行..
</div>

<div id="_mcePaste">
  最好的地方是可以在客戶端執行..
</div>

<div id="_mcePaste">
  又不需要客戶端的電腦上安全 <strong>SQL Server 2000 </strong>有關<strong>DTS 的元件</strong>
</div>

<div id="_mcePaste">
  當然要在你的 Project 上的安裝包上做一些動作
</div>

<div id="_mcePaste">
  令到 用戶在安裝程式時 把適當的 <strong>DLL </strong>複製到客戶的系統中&#8230;
</div>

<div id="_mcePaste">
  而我對<strong>DTS </strong>的認識不多&#8230;
</div>

<div id="_mcePaste">
  所以當公司升級了<strong>SQL Server</strong>到<strong>SQL Server 2008</strong> 之後我便開始使用 <strong>SSIS </strong>了
</div>

<div id="_mcePaste">
  誰不知&#8230;當我把 之前寫的<strong>DTS Package</strong> 轉成了<strong>SSIS</strong>
</div>

<div id="_mcePaste">
  當我在客戶的電腦了執行這功能時便出現錯誤信息&#8230;
</div>

<div id="_mcePaste">
  嘗試了很多方法也解決不了&#8230;
</div>

<div id="_mcePaste">
  到最後有朋友說要在客戶的電腦上安裝 <strong>SSIS Service</strong> 才可以執行<strong>SSIS Package</strong>
</div>

<div id="_mcePaste">
  又說不可以在客戶的電腦上安裝<strong>SSIS Service</strong> 因為版權問題 &#8230;ETC
</div>

<div id="_mcePaste">
  Please correct me if my concept is wrong
</div>

<div id="_mcePaste">
  所以最後便想到用<strong>WCF </strong>的做法&#8230;
</div>

<div id="_mcePaste">
  做一個服務端來解決 <strong>SSIS </strong>的問題了..
</div>

<div id="_mcePaste">
  如果大家遇到差不多的問題 可以嘗試用這個<strong>SSIS WCF Services</strong> 看看能不能解決你的問題
</div>

<div id="_mcePaste">
  或者如果你有更好的解決方案..希望你能夠和我們分享
</div>

<div id="_mcePaste">
  <strong>SSIS Service</strong>
</div>

<div id="_mcePaste">
  <a href="http://ssisservices.codeplex.com">http://ssisservices.codeplex.com</a>
</div>

<div id="_mcePaste">
  <strong>ShareChiWaiLib</strong>
</div>

<div id="_mcePaste">
  <a href="http://sharechiwailib.codeplex.com">http://sharechiwailib.codeplex.com</a>
</div>

<div id="_mcePaste">
  當我有空的時候會在程式碼中加入註解
</div>

<div id="_mcePaste">
  和寫多一些文章關於怎樣使用這個 <strong>SSISServices</strong> 和 <strong>ShareChiWaiLib</strong> 的
</div>

<div id="_mcePaste">
  希望大家可以給我一點Feedback 令到這個2個Projects 更完美
</div>

<div id="_mcePaste">
  Happy coding =)
</div>