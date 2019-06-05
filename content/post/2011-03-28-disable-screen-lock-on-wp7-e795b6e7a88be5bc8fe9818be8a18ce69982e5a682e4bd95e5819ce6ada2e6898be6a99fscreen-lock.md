---
id: 1673
title: 'Disable screen lock on WP7 &#8211; 當程式運行時如何停止手機Screen Lock'
date: 2011-03-28T00:00:39+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1673
permalink: '/2011/03/disable-screen-lock-on-wp7-%e7%95%b6%e7%a8%8b%e5%bc%8f%e9%81%8b%e8%a1%8c%e6%99%82%e5%a6%82%e4%bd%95%e5%81%9c%e6%ad%a2%e6%89%8b%e6%a9%9fscreen-lock/'
categories:
  - Window Phone Development
---
在開發手機程式時..有時候發現&#8230;程式其實是在運行中..  
但是由於一段時間沒有**User Interaction**的關係&#8230;  
所以手機會自己**Screen Lock** 鎖上了..

**解決方法**  
大家可以嘗試用以下的code去停止手機的 **Idle Detection**  
那便可以令到你的手機程式在執行&#8230;即使一段時間沒有**User Interaction**  
手機的**Screen Lock** 也不會鎖上  
大家可能要加入 **Microsoft.Phone.Shell** 參考  
之後使用以下的Code去 停用 **Application Idle** 或 **User Idle Detection**

**VB.Net** 

[vb]  
PhoneApplicationService.Current.ApplicationIdleDetectionMode = IdleDetectionMode.Disabled

&#8216;使用了以下的Code即使 使用者沒有和手機的程式進行任何的Interaction手機也不會自動Screen Lock  
PhoneApplicationService.Current.UserIdleDetectionMode = IdleDetectionMode.Disabled  
[/vb]  
**C#**

<pre>[csharp]
PhoneApplicationService.Current.ApplicationIdleDetectionMode = IdleDetectionMode.Disabled;

//使用了以下的Code即使 使用者沒有和手機的程式進行任何的Interaction手機也不會自動Screen Lock
PhoneApplicationService.Current.UserIdleDetectionMode = IdleDetectionMode.Disabled;
[/csharp]

 
Hope you find it useful
</pre>