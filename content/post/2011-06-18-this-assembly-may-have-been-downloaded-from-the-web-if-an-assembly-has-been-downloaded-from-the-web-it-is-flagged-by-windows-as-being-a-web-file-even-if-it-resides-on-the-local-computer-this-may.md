---
id: 1813
title: 'This assembly may have been downloaded from the Web.  If an assembly has been downloaded from the Web, it is flagged by Windows as being a Web file, even if it resides on the local computer. This may prevent it from being used in your project.'
date: 2011-06-18T00:00:48+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1813
permalink: /2011/06/this-assembly-may-have-been-downloaded-from-the-web-if-an-assembly-has-been-downloaded-from-the-web-it-is-flagged-by-windows-as-being-a-web-file-even-if-it-resides-on-the-local-computer-this-may/
categories:
  - .Net Tips And Tricks
  - Window Phone Development
---
最近比較專注在**Windows Phone Development** 上..  
由於自己還是新手..又希望可以更快地完成自己想到的手機Apps..  
所以便好好運用了網上的資源了..  
E.g.  
在**CodePlex** 上有很多十分好用又實的**WP7** 元件..  
**WP7Clipboard** &#8211; 方便大家在**WP7** 上Copy and Paste東西的元件  
今天當我Download 了一個**WP7** 的元件 [dll] 嘗試在我的程式上使用時出現了這個錯誤信息..  
&#8220;<span style="color: #ff0000;"><strong>Error 1 Could not load the assembly file:///D:\Document\VS2010\DLL\WP7_DLL\WP7Clipboard.dll. This assembly may have been downloaded from the Web. If an assembly has been downloaded from the Web, it is flagged by Windows as being a Web file, even if it resides on the local computer. This may prevent it from being used in your project. You can change this designation by changing the file properties. Only unblock assemblies that you trust. See http://go.microsoft.com/fwlink/?LinkId=179545 for more information.</strong></span>&#8221;  
[<img class="alignnone" title="This assembly may have been downloaded from the Web.  If an assembly has been downloaded from the Web, it is flagged by Windows as being a Web file, even if it resides on the local computer. This may prevent it from being used in your project. You can change this designation by changing the file properties. Only unblock assemblies that you trust" src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/31125dd669764b2b9445e811aabfd7a0" alt="" width="890" height="185" />](http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/31125dd669764b2b9445e811aabfd7a0)

之後發現原來是因為安全的關係  
解決方法十分簡單..

只要在這個DLL 上  
按右鍵-> &#8220;**內容/Properties&#8221;**  
[<img class="alignnone" title="Properties" src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/25a58b6fe7e24af39a8cb4806e73a864" alt="" width="466" height="486" />](http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/25a58b6fe7e24af39a8cb4806e73a864)

在這個DLL的 **內容/Properties 視窗** 中  
你會看到 &#8220;**This file came from another computer and might be blocked to help protect this computer**”  
[<img class="alignnone" title="This file came from another computer and might be blocked to help protect this computer" src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0bbf0026058e4f289380eaf078034133" alt="" width="382" height="518" />](http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0bbf0026058e4f289380eaf078034133)

只需要按一下 &#8220;**解除封鎖/ Unblock**&#8221; 按鈕 之後按 &#8220;**套用 / Apply**&#8221; 和 &#8220;**確定/OK**&#8221; 便可  
[<img class="alignnone" title="This file came from another computer and might be blocked to help protect this computer - Unblocked" src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/00a77b1cfaeb4fb9848598898cdfac89" alt="" width="384" height="519" />](http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/00a77b1cfaeb4fb9848598898cdfac89)

之後再次**Complie** 你的**Project** 便可以解決這個問題的

Hope you find it useful