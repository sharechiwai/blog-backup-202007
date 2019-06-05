---
id: 3102
title: 'Android Studio &#8211; Add As Library Error &#8211; IncorrectOperationException: Must not change document outside command or undo-transparent action.'
date: 2014-03-21T00:00:50+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3102
permalink: /2014/03/android-studio-add-as-library-error-incorrectoperationexception-must-not-change-document-outside-command-or-undo-transparent-action/
categories:
  - .Net Tips And Tricks
tags:
  - Android studio
  - Android Studio 0.5.1
  - Windows Azure Mobile Services
---
今天嘗試**Android Studio**上加入 **Windows Azure Mobile Services**的 **SDK**  
當我嘗試把這個**SDK**加入成為**Library** &#8220;**Add As Library**&#8220;時出現了以下的錯誤&#8230;  
又是和之前的問題一樣..把**Android Studio** 升級到 **0.5.1**便出現很多問題了..  
&#8220;<span style="color: #ff0000;"><strong>IncorrectOperationException: Must not change document outside command or undo-transparent action. See com.intellij.openapi.command.WriteCommandAction or com.intellij.openapi.command.CommandProcessor: Must not change document outside command or undo-transparent action. See com.intellij.openapi.command.WriteCommandAction or com.intellij.openapi.command.CommandProcessor</strong></span>&#8221;

做了一會research 之後找到了解決方法..

**解決方法**  
我們可以自行在**build.gradle**上加入以下 **compile files(&#8220;path/filename.jar&#8221;)**的參考便可以了  
E.G. 我的**Windows Azure Mobile Services SDK Library** 的位置是在這裡的 &#8220;**libs\mobileservices-1.1.0.jar**&#8221;  
<img class="alignnone" alt="Windows Azure Mobile Services Path on Android Studio" src="https://i2.wp.com/farm4.staticflickr.com/3831/13252216653_838f52ed4c_o.png?resize=393%2C176" width="393" height="176" data-recalc-dims="1" />  
所以在**build.gradle**上我的設定便會是這樣

[xml]  
compile files(&#8216;libs/mobileservices-1.1.0.jar&#8217;)  
[/xml]

<img class="alignnone" alt="Android Studio - build.gradle - Windows Azure Mobile Services SDK" src="https://i2.wp.com/farm4.staticflickr.com/3753/13252216633_4f0ffccfb6_o.png?resize=495%2C163" width="495" height="163" data-recalc-dims="1" />  
加入了參考後便可以使用 **Windows Azure Mobile Services SDK for Android**了  
E.g.  
在**Activity** 上我可以加入以下的參考 **com.microsoft.windowsazure.mobileservices**

[java]  
import com.microsoft.windowsazure.mobileservices.MobileServiceClient;  
import com.microsoft.windowsazure.mobileservices.MobileServiceTable;  
import com.microsoft.windowsazure.mobileservices.NextServiceFilterCallback;  
import com.microsoft.windowsazure.mobileservices.ServiceFilter;  
import com.microsoft.windowsazure.mobileservices.ServiceFilterRequest;  
import com.microsoft.windowsazure.mobileservices.ServiceFilterResponse;  
import com.microsoft.windowsazure.mobileservices.ServiceFilterResponseCallback;  
import com.microsoft.windowsazure.mobileservices.TableOperationCallback;  
import com.microsoft.windowsazure.mobileservices.TableQueryCallback;  
[/java]

Hope you find it useful