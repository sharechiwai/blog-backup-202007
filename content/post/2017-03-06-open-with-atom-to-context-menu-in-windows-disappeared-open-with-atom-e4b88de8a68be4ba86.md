---
id: 3894
title: '&#8216;Open with Atom&#8217; to context menu in Windows Disappeared &#8211; &#8216;Open with Atom&#8217; 不見了'
date: 2017-03-06T07:02:56+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3894
permalink: '/2017/03/open-with-atom-to-context-menu-in-windows-disappeared-open-with-atom-%e4%b8%8d%e8%a6%8b%e4%ba%86/'
categories:
  - 工作經驗/體驗/工作心得分享
tags:
  - Atom
  - Atom Settings
  - IDE
---
最近又轉回使用**Atom** 來做寫Code的 IDE  
同一部電腦上安裝了**Atom**, **Visual Studio Code** 和 **SublimeText**  
比較常用的是**VSCode** 和 **Atom**.

由於解決了之前不能安裝 Atom <span class="css-truncate-target"><a href="https://atom.io/packages/atom-beautify">atom-beautify</a></span>

這個十分好用的**Code Formatting Atom package**  
所以便轉回使用 Atom了  
發現&#8230; 我的電腦在文件或資料夾上 Mouse right click 只有 &#8220;**Open with Code**&#8221; 而沒有 &#8220;**Open with Atom**&#8221;  
[<img class="alignnone size-full wp-image-3895" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/NOOpenWithAtom.png?resize=422%2C408" alt="Windows Explorer Context menu do not have 'Open with Atom' Option" width="422" height="408" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/NOOpenWithAtom.png?w=422 422w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/NOOpenWithAtom.png?resize=300%2C290 300w" sizes="(max-width: 422px) 100vw, 422px" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/NOOpenWithAtom.png)  
這個十分不方便..因為每次使用**Atom** 來開啟 Project都要在 **Atom IDE** 內的 **File Menu** 來開  
做了一會research 之後終於找到了解決方法

**解決方法**  
我們可以在**Atom IDE  **的 **Setting** 上  
E.G.  
&#8220;**File**&#8221; -> &#8220;**Settings**&#8221;  
之後選擇&#8221;**System**&#8221; 分頁  
只要選擇便可以了  
&#8211; <span style="color: #008000;"><strong>Show in file context menus</strong></span>  
&#8211; <span style="color: #008000;"><strong>Show in folder context menus</strong></span>  
<img class="alignnone size-full wp-image-3897" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/AtomSystemContextMenu.png?resize=625%2C466" alt="Atom Settings -> System, to update the Enable Context menu options on Windows Explorer" width="625" height="466" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/AtomSystemContextMenu.png?w=843 843w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/AtomSystemContextMenu.png?resize=300%2C224 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/AtomSystemContextMenu.png?resize=768%2C573 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/AtomSystemContextMenu.png?resize=624%2C466 624w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />  
我們再嘗試一次

<img class="alignnone size-full wp-image-3896" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/OpenWithAtom.png?resize=567%2C547" alt="Windows Explorer Context menu has 'Open with Atom' Option" width="567" height="547" srcset="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/OpenWithAtom.png?w=567 567w, https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/03/OpenWithAtom.png?resize=300%2C289 300w" sizes="(max-width: 567px) 100vw, 567px" data-recalc-dims="1" /> 

Hope you find it useful

&nbsp;