---
id: 3063
title: 'Netbean &#8211; Invalid jdkhome specified'
date: 2014-02-16T00:00:29+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3063
permalink: /2014/02/netbean-invalid-jdkhome-specified/
categories:
  - Java
tags:
  - Android studio
  - Netbean
---
自從安裝了**Android studio** 和把 **JAVA JDK** 轉為 **64bit** 之後  
每當我開啟**Netbean** 時便出現以下錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Invalid jdkhome specified</strong></span>&#8221;  
<img class="alignnone" alt="Invalid JDKHOME Specified Netbean" src="https://i0.wp.com/farm8.staticflickr.com/7347/12740820674_5f01a67805_d.jpg?resize=394%2C185" width="394" height="185" data-recalc-dims="1" />  
&#8220;<span style="color: #ff0000;"><strong>Cannot locate Java installation in specified jdkhome:</strong></span>  
<span style="color: #ff0000;"><strong>Do you want to try to use default version</strong></span>&#8221;

我想應該是因為舊的 **JAVA JDK** 被 安裝**Android Studio**時**Uninstall/ 解除安裝**了  
所以找不到原有的**Reference**  
我嘗試在電腦上找 &#8220;**jdkhome**&#8221; 這個環境變數..可惜找不到

做了一會兒research 之後終於找到了解決方法了

**解決方法**

我們可以 **jdkhome** 的變數是 儲存在**Netbean**的設定檔內的 &#8220;**netbeans.conf**&#8221;

<img class="alignnone" alt="Netbeans.conf" src="https://i1.wp.com/farm8.staticflickr.com/7363/12740494713_731ae37c7c_d.jpg?resize=500%2C262" width="500" height="262" data-recalc-dims="1" /> 

以下是他們大概在電腦上的位置  
**64 bits**  
**<span style="color: #0000ff;">C:\Program Files\NetBeans [Version Number]\etc\netbeans.conf</span>**

**32 bits**  
**<span style="color: #0000ff;">C:\Program Files (x86)\NetBeans [Version Number]\etc\netbeans.conf</span>**

E.g. 我的是這樣的  
<span style="color: #0000ff;"><strong>C:\Program Files\NetBeans 7.4\etc\netbeans.conf</strong></span>

開啟後找 &#8220;**jdkhome**&#8221; 這個變數  
之後更新他所參考的 **JDK** 路徑便可以了..

由於這個檔案是儲存在 **C Drive**上..  
所以你可能需要有 &#8220;**Admintrator Permission** /**管理員權限**&#8220;才可以 儲存/修改這個檔案  
否則會出現以下的錯誤信息

&#8220;<span style="color: #ff0000;"><strong>Error saving netbeans.conf &#8211; Access is denied</strong></span>&#8221;  
<img class="alignnone" alt="Error saving netbeans.conf - Access is denied" src="https://i2.wp.com/farm6.staticflickr.com/5485/12740348325_c892d343ce_d.jpg?resize=500%2C262" width="500" height="262" data-recalc-dims="1" /> 

我的做法是先把這個檔案複製到**Desktop**上..  
修改完後再複製到這個資料夾內

他們會問你是不是用&#8221;**Admintrator Permission** /**管理員權限**&#8220;來 取代這個檔案等等

再次開啟**Netbean** 後便不會出現那個錯誤信息了

Hope you find it useful