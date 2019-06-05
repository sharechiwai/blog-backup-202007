---
id: 3885
title: 'Bash Ubuntu create symbolick link to my document &#8211; 如何在Bash on Ubuntu on Windows 上去Windows 的 My Documents Folder'
date: 2017-03-05T09:43:45+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3885
permalink: '/2017/03/bash-ubuntu-create-symbolick-link-to-my-document-%e5%a6%82%e4%bd%95%e5%9c%a8bash-on-ubuntu-on-windows-%e4%b8%8a%e5%8e%bbwindows-%e7%9a%84-my-documents-folder/'
categories:
  - UBuntu
tags:
  - Bash
  - Bash on Ubuntu on Windows
  - symbolic link
  - Ubuntu
---
在**Windows** 上的 **Ubuntu Bash** 怎樣去到**Windows** 的 My Documents

**解決方法**  
大家可以用以下**command** 去到自己的 &#8220;**My Computer**&#8221;  
可以看到電腦有的Drive

<pre>cd /mnt
</pre>

如果想去到**My document**可以輸入以下指令

<pre>cd /mnt/c/Users/[Your username]/Documents
</pre>

[<img class="alignnone size-full wp-image-3887" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/LongPathToDocumentFolder.png?resize=504%2C74" alt="Bash on Ubuntu on Windows , Path to My Document" width="504" height="74" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/LongPathToDocumentFolder.png?w=504 504w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/LongPathToDocumentFolder.png?resize=300%2C44 300w" sizes="(max-width: 504px) 100vw, 504px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/LongPathToDocumentFolder.png)  
為了方便自己我在**Bash** 的 user directory上建立了一個symbolic link  
就像**Windows 的Short-cut**一樣  
待將來輸入 <span style="color: #008080;"><strong>cd doc</strong></span>  
便可以去到我們**Windows** 上的**Documents folder**

**解決方法**

<pre>ln -s '/mnt/c/Users/[Your username]/Documents' doc
</pre>

之後在**Bash**上入輸入 <span style="color: #008080;"><strong>ls</strong></span> 便可以看到那個 **symbolic link** 了  
<img class="alignnone size-full wp-image-3888" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/symlinkOnBash.png?resize=625%2C57" alt="symbolic link" width="625" height="57" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/symlinkOnBash.png?w=646 646w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/symlinkOnBash.png?resize=300%2C27 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/symlinkOnBash.png?resize=624%2C57 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
Hope you find it useful