---
id: 1991
title: 'Visual Studio hang/crash &#8211; Visual Studio 常常出現問題'
date: 2011-08-22T00:00:50+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1991
permalink: '/2011/08/visual-studio-hangcrash-visual-studio-%e5%b8%b8%e5%b8%b8%e5%87%ba%e7%8f%be%e5%95%8f%e9%a1%8c/'
categories:
  - .Net Tips And Tricks
tags:
  - troubleshooting
  - visual studio
  - Visual Studio 2010
---
在網上有很多朋友都在說..他們的**Visual Studio** 升級後出現問題  
有很多時候時因為升級時舊的**Visual Studio** 有些**Visual Studio 2010** 不支援的**Adds-on/Plugin** 所以造成的. 或者有時侯 **Visual Studio** 的設定檔亂了.. 所以出現問題.

當有大至相同的問題出現時.. 可以嘗試做以下的步驟

**解決方法**:  
按 &#8220;**開始/Start Menu**&#8221; -> &#8220;**所有程式集/All Programs**&#8221; -> &#8220;**Microsoft Visual Studio 2010**&#8221; -> &#8220;**Visual Studio 工具 / Visual Studio Tools**&#8221;  
Right Click &#8220;**Visual Studio 命令行 (2010) / Visual Studio Command Prompt (2010)**&#8221;  
之後選擇&#8221;**以管理員身份執行 / Run as Administrator**&#8221;

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/2764379734644120942016866a8195ff/renditions/fullsize.jpg?resize=527%2C521" alt="Visual Studio Command Prompt (2010)" width="527" height="521" data-recalc-dims="1" /> 

之後可以執行以下的指令  
<span style="color: #008000;">#將所有活動記錄至記錄檔中，以進行疑難排解。</span>  
**devenv /log**  
<span style="color: #008000;">#%APPDATA%\Roaming\Microsoft\VisualStudio\\ActivityLog.xml。</span>  
 <span style="color: #008000;">#其中 是 Visual Studio 版本。</span>  
詳情可以參考以下URL  
 <a title="devenv /log" href="http://msdn.microsoft.com/zh-tw/library/ms241272.aspx" target="_blank">http://msdn.microsoft.com/zh-tw/library/ms241272.aspx</a>

<span style="color: #008000;">#還原 Visual Studio 的預設值</span>  
**devenv /resetsettings**  
詳情可以參考以下URL  
 <a title="devenv/ resetsettings" href="http://msdn.microsoft.com/zh-tw/library/ms241273.aspx" target="_blank">http://msdn.microsoft.com/zh-tw/library/ms241273.aspx</a>

<img src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/51b4e94936ae43fc8212567cacab0ab6/renditions/fullsize.jpg?resize=625%2C429" alt="Visual Studio Command resetsettings" width="625" height="429" data-recalc-dims="1" /> 

<span style="color: #008000;">#清除所有選項，以略過使用者加入至 VSPackage 的載入作業 (若使用者不希望載入有問題的 VSPackage)，然後啟動 Visual Studio。</span>  
 <span style="color: #008000;">#若出現 SkipLoading 標記則會停用 VSPackage 的載入作業，而清除該標記則會重新啟用 VSPackage 的載入作業。</span>  
**Devenv /ResetSkipPkgs**  
詳情可以參考以下URL  
 <a title="devenv /resetskippkgs" href="http://msdn.microsoft.com/zh-tw/library/ms241276.aspx" target="_blank">http://msdn.microsoft.com/zh-tw/library/ms241276.aspx</a>

<span style="color: #008000;">#在安全模式 (Safe Mode) 中啟動 Visual Studio，只載入預設的環境和服務。</span>  
<span style="color: #008000;">#這個參數可在 Visual Studio 啟動時，阻止載入所有協力廠商的 VSPackage，以確保穩定執行。</span>  
**devenv /SafeMode**  
詳情可以參考以下URL  
 <a title="devenv /safemode" href="http://msdn.microsoft.com/zh-tw/library/ms241278.aspx" target="_blank">http://msdn.microsoft.com/zh-tw/library/ms241278.aspx</a>

<img src="https://i2.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/621283e09c644ca6b83799f95da45cbf/renditions/fullsize.jpg?resize=625%2C407" alt="Visual Studio Command safemode and ResetSkipPkgs" width="625" height="407" data-recalc-dims="1" />  
如果還是有問題的話  
可以嘗試&#8221;**重新啟動電腦&#8221;**..&#8221;**進入安全模式**&#8220;, 這樣可以排除是 第三方程式 或 驅動程式的影響 ..之後再執行**Visual Studio**  
或是建立新的電腦用戶試試是不是 **User Profile**的問題

**以下是其中一些已經知道能用以上放法解決的問題 **

**1.**  
&#8220;**<span style="color: #ff0000;">QueryService for &#8216;{74946829-37A0-11D2-00C04F8EF4FF}&#8217; failed.&#8217;</span>**  
** <span style="color: #ff0000;">&#8216;針對&#8221;｛74946829-37A0-11D2-00C04F8EF4FF｝&#8221;的QueryService 失敗'&#8221;</span>**

****  
 <span style="color: #000000;">Hope you find it useful&#8221;</span>