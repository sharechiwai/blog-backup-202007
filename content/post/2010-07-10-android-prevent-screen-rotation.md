---
id: 50
title: Android Prevent screen rotation
date: 2010-07-10T13:10:23+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/?p=50
permalink: /2010/07/android-prevent-screen-rotation/
jabber_published:
  - "1282024612"
categories:
  - Android
---
<div id="_mcePaste">
  I have seen lots of <strong>Android </strong>application no matter how you rotate the screen, the screen always in portrait/landscape mode.  I am wondering how to achieve it on my application, because some of the applications do look better if it does not rotate the screen.
</div>

<div id="_mcePaste">
  <strong>Here it is the solution:</strong>
</div>

<div id="_mcePaste">
  On the “<strong>AndroidManifest.xm</strong>l” file
</div>

<div id="_mcePaste">
  You can add <strong>android:screenOrientation=&#8221;portrait&#8221;</strong> to tell the application to prevent screen rotation.
</div>

<div id="_mcePaste">
  E.G.
</div>

<div id="_mcePaste">
  <span style="color:#008000;"><strong>< activity android:name=&#8221;.ShareChiWai&#8221;</strong></span>
</div>

<div id="_mcePaste">
  <span style="color:#008000;"><strong>android:label=&#8221;@string/app_name&#8221; android:configChanges=&#8221;orientation&#8221;</strong></span>
</div>

<div id="_mcePaste">
  <span style="color:#008000;"><strong>android:screenOrientation=&#8221;portrait&#8221; ></strong></span>
</div>

<div id="_mcePaste">
  In this case it will make the application portrait
</div>

<div>
</div>

<div>
  Hope you find it useful
</div>