---
id: 2290
title: 'The Application does not work on Other/Client Machine &#8211; 發布版本的程式在其他的電腦上不能運行'
date: 2011-12-01T00:00:05+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2290
permalink: '/2011/12/the-application-does-not-work-on-otherclient-machine-%e7%99%bc%e5%b8%83%e7%89%88%e6%9c%ac%e7%9a%84%e7%a8%8b%e5%bc%8f%e5%9c%a8%e5%85%b6%e4%bb%96%e7%9a%84%e9%9b%bb%e8%85%a6%e4%b8%8a%e4%b8%8d%e8%83%bd/'
categories:
  - .Net Tips And Tricks
---
有朋友問 為什麼他的程式在發布後..在其他的電腦上不能使用..E.G. 提示..缺小了某個dll/assembile ..etc

其實這是因為你的程式上有一些額外的Library/dll&#8230;  
而在你發布程式時.卻沒有把這些額外的Library/dll&#8230;包含在發布的程式上..

解決方法十分簡單  
**解決方法**:  
**Project** 上按右鍵..選擇 &#8220;**Properties**/&#8221;

<div>
  之後按一下&#8221;<strong>發布</strong>/<strong>Publish</strong>&#8221; tab
</div>

<div>
  再按一下&#8221;<strong>Application Files</strong>&#8220;
</div>

<div>
  之後看看..能不能找到 &#8220;某某xx.dll&#8221; 找到的話
</div>

<div>
  在&#8221;Publish Status&#8221; 上選擇 Include
</div>

<div>
  E.G.
</div>

<div>
  <img src="http://social.microsoft.com/Forums/getfile/8783/" alt="" />
</div>

<div>
  之後再次發佈程式便可以了</p> 
  
  <p>
    Hope you find it useful
  </p>
</div>