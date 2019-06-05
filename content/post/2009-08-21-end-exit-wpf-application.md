---
id: 375
title: End / Exit WPF application
date: 2009-08-21T08:21:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2009/08/21/end-exit-wpf-application
permalink: /2009/08/end-exit-wpf-application/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "6942926503065983456"
categories:
  - .Net Tips And Tricks
---
I create some <span style="font-weight:bold;">WPF application.</span> I am not sure why after I clicked on the <span style="font-weight:bold;">Close icon</span>. It just hides the application, instead of close/exit the application properly. E.g. I can still see the application name on <span style="font-weight:bold;">Task Manager </span>after I closed it.

I added 1 more lines of code to ensure my application closed properly.

Here it is the way I did.  
On the WPF form, I look for the <span style="font-weight:bold;">Window_Closed Event</span> and double click on it. Then it will generate the code which to handle this event.

Then I just added a line on it to force the program to shut down whenever the user click on the close button (<span style="color:rgb(0,0,153);">[X]</span>)

<span style="font-size:85%;"><span style="font-weight:bold;">C# code</span></span>  
<span style="color:rgb(0,102,0);font-size:85%;">private void Window_Closed(object sender, EventArgs e)<br /> {<br /> Application.Current.Shutdown();<br /> }</span>

<span style="font-weight:bold;font-size:85%;">VB.Net code</span>  
   <span style="color:rgb(0,102,0);font-size:85%;">Application.Current.Shutdown()</span>

Happy Programming