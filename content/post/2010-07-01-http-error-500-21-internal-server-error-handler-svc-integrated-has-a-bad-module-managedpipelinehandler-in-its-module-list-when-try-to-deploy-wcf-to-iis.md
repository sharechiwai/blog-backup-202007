---
id: 41
title: 'HTTP Error 500.21 &#8211; Internal Server Error &#8211; Handler &#8220;svc-Integrated&#8221; has a bad module &#8220;ManagedPipelineHandler&#8221; in its module list when try to deploy WCF to IIS'
date: 2010-07-01T07:01:38+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=41
permalink: /2010/07/http-error-500-21-internal-server-error-handler-svc-integrated-has-a-bad-module-managedpipelinehandler-in-its-module-list-when-try-to-deploy-wcf-to-iis/
jabber_published:
  - "1282016678"
categories:
  - .Net Tips And Tricks
  - WCF
---
### After fixing the **HTTP Error 404.3**, I have refreshed my application then I have received another error

<span style="color:#ff0000;"><strong>Error Summary<br /> HTTP Error 500.21 &#8211; Internal Server Error<br /> Handler &#8220;svc-Integrated&#8221; has a bad module &#8220;ManagedPipelineHandler&#8221; in its module list<br /> Error Code    0x8007000d</strong></span>

<div>
  <a href="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/500-21error.png"><img class="alignnone size-full wp-image-42" title="500.21Error" src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/500-21error.png?resize=625%2C578" alt="" width="625" height="578" data-recalc-dims="1" /></a>
</div>

Fortunately, I have managed to fix it.

**Here it is the solution:**

1) Click on &#8220;**Start**&#8221; -> &#8220;**Run**&#8221; -> Enter &#8220;**cmd**&#8221; to launch &#8220;**Command Prompt**&#8221;

2) Type: &#8220;**C:**&#8221; and press &#8220;**Enter**&#8221;

3) Enter the following command on the command prompt  
**cd &#8220;WINDOWSMicrosoft.NETFrameworkv4.0.30319&#8221;** <-for 32bit machine  
**cd &#8220;WINDOWSMicrosoft.NETFramework64v4.0.30319&#8221;** <-for 64bit machine  
The version number maybe different on different machine, at the moment the .net framework which installed on my machine is** _v4.0.30319_**.  
If you could not found it you can try to use the search feature on Windows to local &#8220;**aspnet_regiis.exe**&#8221; file  
4) Then you can enter the following command to register asp.net to your IIS server  
&#8220;**aspnet_regiis.exe -i**&#8221;  
[<img class="alignnone size-full wp-image-43" title="installasp.netiis" src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/installasp-netiis.png?resize=625%2C315" alt="" width="625" height="315" data-recalc-dims="1" />](https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/installasp-netiis.png)

<div>
  Once you have installed it you should be able to view the <strong>WCF </strong>service which you deployed to your <strong>IIS</strong> server.
</div>

Hope you found it useful