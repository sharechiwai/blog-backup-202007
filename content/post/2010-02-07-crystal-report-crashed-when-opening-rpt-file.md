---
id: 323
title: Crystal Report Crashed When Opening .rpt file
date: 2010-02-07T02:07:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/02/07/crystal-report-crashed-when-opening-rpt-file
permalink: /2010/02/crystal-report-crashed-when-opening-rpt-file/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "5877032068377171022"
categories:
  - Crystal Report Tips and Tricks
---
<span class="Apple-style-span" style="font-family:'Times New Roman';font-size:16px;"></span>

<div style="margin-bottom:0;margin-top:0;">
  I am having a problem on my crystal report 11.5. The application that I create cannot load the Crystal Report file, when i try to open a crystal report file(.rpt) that I created a year ago.[which i have edited last week.] 
</div>

<div style="margin-bottom:0;margin-top:0;">
</div>

<div style="margin-bottom:0;margin-top:0;">
  All of sudden, it just started to crash the Crystal Report application as soon as I open it. 
</div>

<div style="margin-bottom:0;margin-top:0;">
  <img height="264" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/a6aed1472ab545f184f85de8e20a657f" width="419" /></p> 
  
  <p>
    <img height="204" src="http://api.photoshop.com/home_453edadf42c44e2bba351fb5d2dfaeb1/adobe-px-assets/94e62d64ad1d4a7e986dae54d42575bc" width="444" /></div> 
    
    <div style="margin-bottom:0;margin-top:0;">
      I have asked my friend to open the same file on his machine and it works&#8230; (This .rpt is stored on the network drive). I guess it is something wrong on my computer.
    </div>
    
    <div style="margin-bottom:0;margin-top:0;">
    </div>
    
    <div style="margin-bottom:0;margin-top:0;">
      However, i remember that I had silimar issue before, which is caused by the default printer.
    </div>
    
    <div style="margin-bottom:0;margin-top:0;">
    </div>
    
    <div style="margin-bottom:0;margin-top:0;">
      Here it is my solution.
    </div>
    
    <div style="margin-bottom:0;margin-top:0;">
      <ol>
        <li>
          <b>Start</b>-> <b>Devices and Printers or [Printers and Faxes]</b>
        </li>
        <li>
          Select an alternative <b>printer</b> as your <b>default printer</b>.
        </li>
        <li>
          Try to open up the .rpt again. It should works.
        </li>
      </ol>
    </div>
    
    <div style="margin-bottom:0;margin-top:0;">
      Hope this can help =)
    </div>