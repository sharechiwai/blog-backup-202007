---
id: 1145
title: 'Fatal error: Call to undefined function anchor() in Codeingter'
date: 2011-02-18T07:55:55+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=1145
permalink: /2011/02/fatal-error-call-to-undefined-function-anchor-in-codeingter/
categories:
  - Codeingter
---
<div id="_mcePaste">
  在嘗試<strong>Codeingter</strong>的時候由於自己不太熟識的問係..
</div>

<div id="_mcePaste">
  常常出現問題&#8230;
</div>

<div id="_mcePaste">
  所以在這裡記錄一下 這想問題和解決方法&#8230;
</div>

<div id="_mcePaste">
  有很多的都是很簡單的問題&#8230;SIGH&#8230;
</div>

<div id="_mcePaste">
  可惜我太Stupid了
</div>

<div>
</div>

<div id="_mcePaste">
  今日遇到的問題是
</div>

<div id="_mcePaste">
  當我在<strong>PHP </strong> 中使用
</div>

<div id="_mcePaste">
  <span style="color: #008000;"><? echo anchor(&#8220;Home&#8221;,&#8221;Home&#8221;); ?> |</span>
</div>

<div id="_mcePaste">
  時出現以下的錯誤信息&#8230;
</div>

<div>
  &#8220;<span style="color: #ff0000;"><strong>Fatal error: Call to undefined function anchor() in Codeingter</strong></span>&#8220;
</div>

<div id="_mcePaste">
  由於這是一個很basic 的錯誤&#8230; 解決方法十分簡單&#8230;</p> 
  
  <p>
    <strong>解決方法:</strong><br /> 原來是因為自己大意..忘了 Load這個Helper Class&#8230;</div> 
    
    <div id="_mcePaste">
      只是在<span style="color: #800080;"><strong> Config Folder</strong></span>中的<span style="color: #800080;"><strong>autoload.php</strong></span>上
    </div>
    
    <div id="_mcePaste">
      或到 <span style="color: #008000;"><strong>$autoload[&#8216;helper&#8217;]</strong></span>
    </div>
    
    <div id="_mcePaste">
      之後在<strong>Array</strong>上加上 &#8220;<strong>url</strong>&#8221; 這個Helper Class便可
    </div>
    
    <div id="_mcePaste">
      <span style="color: #008000;"><strong>$autoload[&#8216;helper&#8217;] = array(&#8220;url&#8221;);<br /> </strong></span>
    </div>
    
    <div id="_mcePaste">
      Hope you find it useful
    </div>