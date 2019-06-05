---
id: 3856
title: 'How to delete field inside Json Object &#8211; 如何把Json 的屬性移除'
date: 2017-02-13T07:04:12+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3856
permalink: '/2017/02/how-to-delete-field-inside-json-object-%e5%a6%82%e4%bd%95%e6%8a%8ajson-%e7%9a%84%e5%b1%ac%e6%80%a7%e7%a7%bb%e9%99%a4/'
categories:
  - Javascript
tags:
  - Javascript
  - Javascript Tips and tricks
  - JSON
---
今日在公司經過同事**Code Review**&#8230;我學會了很多東西  
其中一個就是如何**delete Json**/ **Javascript Object** 內的一些Field

e.g.

<pre>var params = {
        UserId: membership.id,
        FirstName: membership.firstName,
        ScreenName: membership.nickname,
        location: membership.currentLocation
      };
</pre>

假設只有某些權限的用戶才可以看到 location這個field的

我們可以使用 **<span style="color: #0000ff;">delete</span> keyword** 來把**Json / Javascript object的 field 移除**  
e.g.

<pre>delete params.location;
console.log(params);
</pre>

Hope you find it useful