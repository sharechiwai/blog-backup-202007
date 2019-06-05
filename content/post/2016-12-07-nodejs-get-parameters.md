---
id: 3779
title: NodeJs Get Parameters
date: 2016-12-07T00:00:08+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3779
permalink: /2016/12/nodejs-get-parameters/
categories:
  - NodeJs
tags:
  - NodeJs
  - NodeJs Express
---
今日既**NodeJs** 筆記是用來記錄一個十分簡單的功能  
就是 **Get Query String**或是取後 **GET** 的 **paramater**.

**解決方法**  
我們可以使用 **req.query[&#8216;ParameterName&#8217;]** 來取得 parameter 的value

<pre>if(req.query['location'] == undefined){
    console.log("No parameter named 'location'");
 }else{
     console.log(locaton);
}
</pre>

Hope you find it useful