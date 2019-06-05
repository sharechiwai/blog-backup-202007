---
id: 328
title: Crystal report PDF font size get reduced/smaller
date: 2010-02-02T02:02:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/02/02/crystal-report-pdf-font-size-get-reducedsmaller
permalink: /2010/02/crystal-report-pdf-font-size-get-reducedsmaller/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "8144523540852447439"
categories:
  - Crystal Report Tips and Tricks
---
<div style="margin:0;">
  I just realised the font/text on PDF which I created by using Crystal report get resized. They displays fine on Crystal report preview screen and they were printed ok. When I try to print the same report from the PDF, the print out looks smaller.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  After trying to fix it on the Crystal Report(Report option) and Adobe Reader(Print option). I realise that the only the Font get resized and all the Images/Box…etc they are all fine.
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Finally, I found out that it is a bug on Crystal Report, it occurs since version 10, (or even eariler).
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Here it is the solutions.
</div>

<div style="margin:0;">
  You need to modify your computer’s registry in order to fix it.
</div>

<div style="margin:0;">
  1) Press “<span style="font-weight:bold;">Start</span>” menu and click on “Run” (In Windows XP)
</div>

<div style="margin:0;">
  2) Type “<span style="font-weight:bold;">regedit</span>” and press Enter to open up Registry Editor
</div>

<div style="margin:0;">
  3) On the Registry Editor click on the “+” on “<span style="font-weight:bold;">HKEY_CURRENT_USER</span>”
</div>

<div style="margin:0;">
  4) Then expand “<span style="font-weight:bold;">Software</span>”-> “<span style="font-weight:bold;">Business Objects</span>”-> “<span style="font-weight:bold;">Suite 11.5</span>”
</div>

<div style="margin:0;">
  5) Click on “Export” and “<span style="font-weight:bold;">PDF</span>” if the PDF folder does not exist here
</div>

<div style="margin:0;">
  6) Right click on “Export” and Select <span style="font-weight:bold;">“New”-> “Key”</span> and rename it as “PDF”
</div>

<div style="margin:0;">
  7) After that right click on “PDF” and click on<span style="font-weight:bold;"> “New”->”DWORD”</span> value and rename it to “<span style="font-weight:bold;">ForceLargerFonts</span>”
</div>

<div style="margin:0;">
  8) Set <span style="font-weight:bold;">1</span> as the value of “<span style="font-weight:bold;">ForceLargerFonts</span>”
</div>

<div style="margin:0;">
  9) Close Registry Editor and restart Crystal Report application
</div>

<div style="margin:0;">
  10) Try to export a PDF and see it the problem has been fixed
</div>

<div style="margin:0;">
</div>

<div style="margin:0;">
  Hope this can help.
</div>