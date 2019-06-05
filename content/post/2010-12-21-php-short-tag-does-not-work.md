---
id: 1152
title: 'PHP  Short tag does not work'
date: 2010-12-21T00:00:58+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1152
permalink: /2010/12/php-short-tag-does-not-work/
categories:
  - Codeingter
  - PHP 新手筆記
---
<div id="_mcePaste">
  由於之前的電腦重新安裝過的關係&#8230;
</div>

<div id="_mcePaste">
  所以電腦上有很多設定都沒有設定好
</div>

<div id="_mcePaste">
  當我嘗試跟隨著一些PHP教學時
</div>

<div id="_mcePaste">
  我的Code出現錯誤&#8230;
</div>

<div id="_mcePaste">
  E.G.
</div>

<div id="_mcePaste">
  <span style="color: #ff0000;"><strong>load->GenerateReport(); ?></strong></span>
</div>

<div id="_mcePaste">
  我原來的Code 是這樣的
</div>

<div id="_mcePaste">
  [php]<? $this->load->GenerateReport(); ?> [/php]</p>
</div>

<div id="_mcePaste">
  還記得之前也遇過相同的問題&#8230;
</div>

<div id="_mcePaste">
  這是和PHP的設定有關的問題
</div>

<div id="_mcePaste">
  解決放法得簡單&#8230;
</div>

<div id="_mcePaste">
  找出你電腦上的<strong><span style="color: #800080;"> PHP.ini</span></strong>
</div>

<div id="_mcePaste">
  之後找到 ”<strong>short_open_tag</strong>”
</div>

<div id="_mcePaste">
  這個settings keyword, 之後把<span style="color: #000000;"><strong>short_open_tag</strong></span>這個設定啟動便可
</div>

<div id="_mcePaste">
  E.G.
</div>

<div id="_mcePaste">
  <span style="color: #008000;"><strong>; Default Value: On</strong></span>
</div>

<div id="_mcePaste">
  <span style="color: #008000;"><strong>; Development Value: Off</strong></span>
</div>

<div id="_mcePaste">
  <span style="color: #008000;"><strong>; Production Value: Off</strong></span>
</div>

<div id="_mcePaste">
  <span style="color: #008000;"><strong>; http://php.net/short-open-tag</strong></span>
</div>

<div id="_mcePaste">
  <span style="color: #000080;"><strong>short_open_tag = Off<br /> <a href="https://i2.wp.com/farm6.static.flickr.com/5289/5367639755_53158d2116.jpg"><img class="alignnone" title="PHP.ini" src="https://i2.wp.com/farm6.static.flickr.com/5289/5367639755_53158d2116.jpg?resize=500%2C321" alt="" width="500" height="321" data-recalc-dims="1" /></a></p> 
  
  <p>
    </strong></span></div> 
    
    <div id="_mcePaste">
      Hope you find it useful
    </div>
    
    <div id="_mcePaste">
      <strong><br /> 溫馨提示:</strong>
    </div>
    
    <div id="_mcePaste">
      如果可以的話..
    </div>
    
    <div id="_mcePaste">
      我不建議大家使用Short Tag&#8230;
    </div>
    
    <div id="_mcePaste">
      因為如果你是用其他的Hosting 公司時..
    </div>
    
    <div id="_mcePaste">
      他們未必有啟用short_open_tag 這個功能的&#8230;
    </div>
    
    <div id="_mcePaste">
      所以用傳統的方法比較安全
    </div>