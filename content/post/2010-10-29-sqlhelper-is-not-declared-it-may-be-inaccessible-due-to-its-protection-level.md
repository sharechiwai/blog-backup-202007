---
id: 815
title: '&#8216;SQLHelper&#8217; is not declared. It may be inaccessible due to its protection level.'
date: 2010-10-29T00:00:53+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=815
permalink: /2010/10/sqlhelper-is-not-declared-it-may-be-inaccessible-due-to-its-protection-level/
categories:
  - .Net Tips And Tricks
---
<div id="_mcePaste">
  今天把一個由<strong>VS2005 .Net Framework 2.0</strong> 寫的程式
</div>

<div id="_mcePaste">
  重新用 <strong>VS2010 </strong>寫的時候&#8230;
</div>

<div id="_mcePaste">
  在更用<strong>ShareChiWaiLib</strong> 時
</div>

<div id="_mcePaste">
  出現了這個錯誤信息..
</div>

<div id="_mcePaste">
  <span style="color: #ff0000;"><strong>&#8216;SQLHelper&#8217; is not declared. It may be inaccessible due to its protection level.<br /> </strong></span>
</div>

<div id="_mcePaste">
  和以下的 Warning
</div>

<div id="_mcePaste">
  <span style="color: #ff0000;"><strong>Namespace or type specified in the Imports &#8216;ShareChiWaiLib&#8217; doesn&#8217;t contain any public member or cannot be found. Make sure the namespace or the type is defined and contains at </strong></span><span style="color: #ff0000;"><strong>least one public member. Make sure the imported element name doesn&#8217;t use any aliases.</strong></span>
</div>

<div id="_mcePaste">
  <span style="color: #ff0000;"><strong>The referenced assembly &#8220;ShareChiWaiLib&#8221; could not be resolved because it has a dependency on &#8220;System.Web, Version=4.0.0.0, Culture=neutral,</strong></span>
</div>

<div id="_mcePaste">
  <span style="color: #ff0000;"><strong>PublicKeyToken=b03f5f7f11d50a3a&#8221; which is not in the currently targeted framework &#8220;.NETFramework,Version=v4.0,Profile=Client&#8221;. Please remove references to assemblies not in the </strong></span><span style="color: #ff0000;"><strong>targeted framework or consider retargeting your project.</strong>&nbsp;</p> 
  
  <p>
    <strong><a href="https://i1.wp.com/farm6.static.flickr.com/5225/5691038335_5df74391f4.jpg"><img class="alignnone size-full wp-image-817" title="ClientProfileError" src="https://i1.wp.com/farm6.static.flickr.com/5225/5691038335_5df74391f4.jpg?w=625" alt="" data-recalc-dims="1" /></a></strong>
  </p>
  
  <p>
    <strong> </strong><strong> </strong>
  </p>
  
  <p>
    &nbsp;
  </p>
  
  <p>
    </span></div> 
    
    <div id="_mcePaste">
      我便在想..我在其他程式中也選用 這個 ShareChiWaiLib 的 SQLHelper 來處理一些和SQL 相關的 程序&#8230;
    </div>
    
    <div id="_mcePaste">
      不知道為何在這個新建立的應用程式才出現問題&#8230;
    </div>
    
    <div id="_mcePaste">
      最後終於找到了解決方法
    </div>
    
    <div id="_mcePaste">
      其實這是因為我的<strong>Visual Studio 2010 </strong>的Default Setting 是用<strong> .Net Framework 4 Client Profile</strong>
    </div>
    
    <div id="_mcePaste">
      而有些 <strong>.Net Framework assemblies </strong>又不在<strong>.Net Framework 4 Client Profile</strong>
    </div>
    
    <div id="_mcePaste">
      所以便出現這個 問題了
    </div>
    
    <div id="_mcePaste">
      <strong><br /> 解決方法:</strong>
    </div>
    
    <div id="_mcePaste">
      打開你的<strong>Project </strong>內容 E.G. 雙按 &#8220;<strong>My Project</strong>&#8220;
    </div>
    
    <div id="_mcePaste">
      之後選擇 &#8220;<strong>Compile Tab 分頁</strong>&#8220;
    </div>
    
    <div id="_mcePaste">
      按一下&#8221;<strong>Advanced Compile Options</strong>&#8221;<br /> <a href="https://i0.wp.com/farm6.static.flickr.com/5144/5691610636_7950db5685.jpg"><img class="alignnone size-large wp-image-818" title="CompilerOption" src="https://i0.wp.com/farm6.static.flickr.com/5144/5691610636_7950db5685.jpg?fit=625%2C625" alt="" data-recalc-dims="1" /></a>
    </div>
    
    <div id="_mcePaste">
      在 <strong>Target framework (all configurations):</strong> 的選項中選擇
    </div>
    
    <div id="_mcePaste">
      &#8220;<strong>.NET Framework 4</strong>&#8221; 便可<br /> <a style="font-family: Georgia, 'Bitstream Charter', serif; color: #0066cc; line-height: 1.5;" href="https://i1.wp.com/farm6.static.flickr.com/5189/5691038255_b467246010.jpg"><img class="alignnone size-full wp-image-819" style="font-family: Georgia, 'Bitstream Charter', serif; color: #444444; line-height: 1.5; max-width: 640px; margin: 0px; border: 0px initial initial;" title="AdvancedCompilerSettings" src="https://i1.wp.com/farm6.static.flickr.com/5189/5691038255_b467246010.jpg?w=625" alt="" data-recalc-dims="1" /></a>
    </div>
    
    <div id="_mcePaste">
      Hope you find it useful
    </div>