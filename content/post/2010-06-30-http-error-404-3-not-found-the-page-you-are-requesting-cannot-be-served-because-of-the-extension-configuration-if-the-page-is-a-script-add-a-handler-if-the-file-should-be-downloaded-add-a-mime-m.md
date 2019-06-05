---
id: 87
title: 'HTTP Error 404.3 &#8211; Not Found The page you are requesting cannot be served because of the extension configuration. If the page is a script, add a handler. If the file should be downloaded, add a MIME map. Error Code 0x80070032. When try to use IIS to host WCF services'
date: 2010-06-30T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/06/30/http-error-404-3-not-found-the-page-you-are-requesting-cannot-be-served-because-of-the-extension-configuration-if-the-page-is-a-script-add-a-handler-if-the-file-should-be-downloaded-add-a-mime-m
permalink: /2010/06/http-error-404-3-not-found-the-page-you-are-requesting-cannot-be-served-because-of-the-extension-configuration-if-the-page-is-a-script-add-a-handler-if-the-file-should-be-downloaded-add-a-mime-m/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "4542528945592975854"
categories:
  - WCF
---
When I try to deploy the **WCF** application which I created in **VS2010** to the development machine that is using **Win7 64bit and IIS 7.5**, I have received the following error message. 

<div style="color:red;">
  <b>HTTP Error 404.3 &#8211; Not Found</b>
</div>

<div style="color:red;">
  <b>The page you are requesting cannot be served because of the extension configuration. If the page is a script, add a handler. If the file should be downloaded, add a MIME map.</b><br /><b>Error Code: 0x80070032</b>
</div>



<div class="separator" style="clear:both;text-align:center;">
</div>

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/404-3mimetype.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="576" src="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/404-3mimetype.png?resize=625%2C576" width="625" data-recalc-dims="1" /></a>
</div>

As I am a absolute beginner in creating a WCF. I have no idea what have a done wrong.  
I used **Microsoft Web Platform** to set up the **IIS Web Server** and then I published into a file system, so that I can copy and paste it to the web-server like what I did when I publish a web-application.  
Finally I have realise it is something to do with the extension configuration / **MIME map**. I guess something is missing on the web server.

Here it is the solution.  
1)  Click on &#8220;**Start**&#8221; Menu -> &#8220;**Control Panel**&#8221; -> &#8220;**Programs and Features**&#8220;  
or paste the line below, onto your **address bar** and press **Enter**  
 &#8220;**<span style="color:#38761d;">Control PanelAll Control Panel ItemsPrograms and Features</span>**&#8221; 

<div class="separator" style="clear:both;text-align:center;">
  <a href="http://sharechiwai.files.wordpress.com/2010/06/enablewcf.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="348" src="http://sharechiwai.files.wordpress.com/2010/06/enablewcf.png?w=300&#038;resize=400%2C348" width="400" data-recalc-dims="1" /></a>
</div>

2) Click on &#8220;**Turn Windows features on or off**&#8220;  
3) On the &#8220;**Windows Features**&#8221; window,  
4) Expands &#8220;**Microsoft .Net Framework 3.5.1**&#8221; or &#8220;**Microsoft .Net Framework 3.0**&#8221; depends on which version of windows you are using  
5) Tick &#8220;**Windows Communication Foundation HTTP Activation**&#8221;  and &#8220;**Windows Communication Foundation Non-HTTP Activation**&#8220;  
6) click &#8220;**OK**&#8221; and try to refresh the webpage.

If you are using older version of **Windows Server** E.g. 2003/ **WinXP**, you can try to use command prompt.  
1) Click on &#8220;**Start**&#8221; -> &#8220;**Run**&#8221; -> Enter &#8220;**cmd**&#8221; to launch &#8220;**Command Prompt**&#8220;  
2) Type: &#8220;**C:**&#8221; and press &#8220;**Enter**&#8220;  
3) Enter the following command on the command prompt  
**cd &#8220;windowsMicrosoft.NetFrameworkv3.0Windows Communication Foundation&#8221;**  
4) Then you can enter the following command to setup WCF on your computer.  
&#8220;**servicemodelref -i**&#8220;

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/servicemoderegi.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="404" src="https://i1.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/servicemoderegi.png?resize=625%2C404" width="625" data-recalc-dims="1" /></a>
</div>

5)Then you should see a similar screen as above.

If everything setup properly on you server, you should be able to view the **WCF** service you have deployed to the **IIS**.

However&#8230;Once I solved the **HTTP Error 404.3** error I have received another error like below.

<div style="color:red;">
  <b>HTTP Error 500.21 &#8211; Internal Server Error</b>
</div>

<div style="color:red;">
  <b>Handler &#8220;svc-Integrated&#8221; has a bad module &#8220;ManagedPipelineHandler&#8221; in its module list</b>
</div>

<div style="color:red;">
  <b>Error Code 0x8007000d</b>
</div>

<div class="separator" style="clear:both;text-align:center;">
  <a href="http://sharechiwai.files.wordpress.com/2010/06/500-21error.png" style="margin-left:1em;margin-right:1em;"><img border="0" height="574" src="http://sharechiwai.files.wordpress.com/2010/06/500-21error.png?w=300&#038;resize=625%2C574" width="625" data-recalc-dims="1" /></a>
</div>

I will explain how I solve it in my next post.  
[HTTP Error 500.21 &#8211; Internal Server Error Handler &#8220;svc-Integrated&#8221; has a bad module &#8220;ManagedPipelineHandler&#8221; in its module list](http://sharechiwai.blogspot.com/2010/07/http-error-50021-internal-server-error.html) 

Hope you found it useful