---
id: 137
title: 'Android &#8211; check if the device is connected to internet.'
date: 2010-05-13T00:00:00+08:00
author: ShareChiWai
layout: post
guid: http://sharechiwai.wordpress.com/2010/05/13/android-check-if-the-device-is-connected-to-internet
permalink: /2010/05/android-check-if-the-device-is-connected-to-internet/
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "1606158027532738814"
categories:
  - Android
---
If you want to check if your device is connected to the internet, you would need to have the permission below, to check the network statue.

<uses-permission android:name="**android.permission.ACCESS\_NETWORK\_STATE**&#8220;>

Then you create a **ConnectivityManager** Object to retrieve Network information.

<div style="color:#38761d;">
  <b>public static boolean IsConnectedToInternet(){</b>
</div>

<div style="color:#38761d;">
  <b>        boolean result = false;</b>
</div>

<div style="color:#38761d;">
  <b>        ConnectivityManager ConnectionInfo = (ConnectivityManager) this.getSystemService(Context.CONNECTIVITY_SERVICE);</b>
</div>

<div style="color:#38761d;">
  <b>        NetworkInfo info = ConnectionInfo.getActiveNetworkInfo();</b>
</div>

<div style="color:#38761d;">
  <b>        if (info!=null && info.isConnected()){</b>
</div>

<div style="color:#38761d;">
  <b>            result = true;</b>
</div>

<div style="color:#38761d;">
  <b>        }</b>
</div>

<div style="color:#38761d;">
  <b>        return result;</b>
</div>

<div style="color:#38761d;">
  <b>    }</b>
</div>

Hope you find it useful. If you have a better way to check if the device is connected to the internet. Please leave me a message, so that I can improve my code =).

Happy coding.