---
id: 3670
title: '&#8216;scp&#8217; is not recognized as an internal or external command &#8211; 如何在Windows 命令提示符 上使用 scp'
date: 2016-05-23T00:00:36+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3670
permalink: '/2016/05/scp-is-not-recognized-as-an-internal-or-external-command-%e5%a6%82%e4%bd%95%e5%9c%a8windows-%e5%91%bd%e4%bb%a4%e6%8f%90%e7%a4%ba%e7%ac%a6-%e4%b8%8a%e4%bd%bf%e7%94%a8-scp/'
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Intel Edison
  - IoT
  - NodeJs
  - RaspberryPi
  - SCP
---
最近嘗試跟隨一個網上教學去把電腦上的**NodeJs code** **deploy**/ copy到 **Intel Edison** / **Raspberry Pi**  
上  
他的指令是這樣的  
&#8220;**<span style="color: #008000;">scp</span>** [**<span style="color: #ff0000;">fileName</span>**] [<span style="color: #008000;"><strong>copy to filename, 通嘗是 root@URL_IPAddress:~/FilePath]</strong></span>&#8221;  
但是當我執行  
**scp**這個指令是他出現了以下的錯誤信息  
&#8220;&#8216;<span style="color: #ff0000;"><strong>scp&#8217; is not recognized as an internalor external command, operable program or batch file</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm8.static.flickr.com/7024/27092598862_a950c64e3c_z.jpg?resize=625%2C199" alt="'scp' is not recognized" width="625" height="199" data-recalc-dims="1" /> 

**解決方法**十分簡單.  
跟上一次介紹

### <a href="http://blog.sharechiwai.com/2016/05/ssh-is-not-recognized-as-an-internal-or-external-command-%e5%a6%82%e4%bd%95%e5%9c%a8windows-%e5%91%bd%e4%bb%a4%e6%8f%90%e7%a4%ba%e7%ac%a6-%e4%b8%8a%e4%bd%bf%e7%94%a8-ssh/" rel="bookmark">‘ssh’ is not recognized as an internal or external command – 如何在Windows 命令提示符 上使用 SSH</a> {.entry-title}

我們可以使用**Git**的 **Usr/Bin** 資料夾入的 程式便可以

相信很多**Developer**都有使用**Git**的  
如果唔有的話可以到以下網址 下載及安裝**Git**  
<https://git-scm.com/downloads>

安裝完成後..便可以在**Windows** 的 **Environment Path** **環境變數**上的 “**Path**“變數上加上  
**Git\usr\bin** 的路徑  
因為這個路徑上存有很多有用的工具/程式  
E.G  
**C:\Program Files\Git\usr\bin  
<img class="alignnone" src="http://i2.wp.com/farm8.static.flickr.com/7520/26913335540_df8d7caed7_z.jpg?zoom=1.5&resize=625%2C220" srcset="http://i2.wp.com/farm8.static.flickr.com/7520/26913335540_df8d7caed7_z.jpg?zoom=1.5&resize=625%2C220" alt="Git User Bin Path" width="625" height="220" />  
** 

按下”**確定**“便可以了  
<img class="alignnone" src="http://i1.wp.com/farm8.static.flickr.com/7645/27154825246_38d8b57616_z.jpg?zoom=1.5&resize=574%2C640" srcset="http://i1.wp.com/farm8.static.flickr.com/7645/27154825246_38d8b57616_z.jpg?zoom=1.5&resize=574%2C640" alt="Add Environment Variable on Windows 10 for Git User Bin" width="574" height="640" /> 

之後再次執行 &#8220;**scp**&#8221; 應該會成功的  
<img class="alignnone" src="https://i1.wp.com/farm8.static.flickr.com/7190/27154825506_cf54fbab30_z.jpg?resize=625%2C133" alt="scp working on Windows" width="625" height="133" data-recalc-dims="1" />  
Hope you find it useful