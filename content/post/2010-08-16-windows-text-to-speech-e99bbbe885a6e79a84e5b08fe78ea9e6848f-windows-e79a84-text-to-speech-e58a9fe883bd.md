---
id: 32
title: 'Windows Text-To-Speech &#8211; 電腦的小玩意 Windows 的 Text To Speech 功能'
date: 2010-08-16T08:31:39+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=32
permalink: '/2010/08/windows-text-to-speech-%e9%9b%bb%e8%85%a6%e7%9a%84%e5%b0%8f%e7%8e%a9%e6%84%8f-windows-%e7%9a%84-text-to-speech-%e5%8a%9f%e8%83%bd/'
jabber_published:
  - "1281962665"
delicious:
  - 's:78:"a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1282677963";}";'
categories:
  - Windows
  - 電腦小貼事 Computing Tips and Tricks
---
今天在網上學到了一個電腦的小玩意

就是利用 **Microsoft Windows** 的 **Speech Recognition Options** 中的 **Text to Speech** 功能來讀一些文字出來  
[暫時我只時試過可以讀英文和數字]  
不知道能不能讀到中文呢

大家可以嘗試用打開 &#8220;**記事本**&#8221; [**notepad**]  
之後輸入以下文字  
<span style="color:#008000;">CreateObject(&#8220;SAPI.SpVoice&#8221;).speak &#8220;ShareChiWai Say Hello to You&#8221;</span>  
[<img class="alignnone size-full wp-image-34" title="ttsTxt" src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/ttstxt.jpg?resize=625%2C138" alt="" width="625" height="138" data-recalc-dims="1" />](https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/ttstxt.jpg)  
之後把文字檔儲存成 &#8220;**sharechiwaitrick.vbs**&#8221;  
最重要的是把副檔案名 存成 &#8220;**.vbs**&#8221;  
要儲存成&#8221;**.vbs**&#8221;  
你要把 &#8220;**save as type**&#8221; 轉成 &#8220;**All Files (\*.\*)**&#8221; 否則電腦用把這個檔案的副檔案名自動加上&#8221;**.txt**&#8221;  
[<img class="alignnone size-full wp-image-33" title="Save as .vbs" src="https://i0.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/saveas.jpg?resize=610%2C175" alt="" width="610" height="175" data-recalc-dims="1" />](https://i0.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/saveas.jpg)

之後只要用 **Mouse double click/滑鼠雙按** 開啟 這個 &#8220;sharechiwaitrick.vbs&#8221;檔案  
便會聽到電腦讀出剛才你輸入的文字

傳聞: 電腦也有男女之分的  
看看讀出文字的是男聲還是女聲吧 =)

Hope you find it interesting