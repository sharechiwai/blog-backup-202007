---
id: 806
title: 'Cross-thread operation not valid: Control &#8216;Button1&#8217; accessed from a thread other than the thread   it was created on.'
date: 2010-10-08T00:00:43+08:00
author: ShareChiWai
layout: post
guid: http://oldblog.sharechiwai.com/?p=806
permalink: /2010/10/cross-thread-operation-not-valid-control-button1-accessed-from-a-thread-other-than-the-thread-it-was-created-on/
categories:
  - .Net Tips And Tricks
---
今日在嘗試用**Threading** 寫一個線程的功能是  
出現以下的**Error Message**

<span style="color: #ff0000;"><strong>&#8220;Cross-thread operation not valid: Control &#8216;Button1&#8217; accessed from a thread other than the thread it was created on.&#8221;</strong><br /> </span>  
之後回想起之前用BackGroundWorker 時也遇過相同的問題  
解決方法很簡單:  
就是在 **Form.Load Event** 或 當你**初始化你的Form** 時  
加入以下的程式碼

<span style="color: #008000;"><strong>Control.CheckForIllegalCrossThreadCalls = False</strong></span>

Hope your find it useful