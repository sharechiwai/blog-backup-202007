---
id: 3420
title: PHP Create Json Object/String 如何使用PHP 來建立 Json Object/String
date: 2015-06-01T00:00:52+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3420
permalink: '/2015/06/php-create-json-objectstring-%e5%a6%82%e4%bd%95%e4%bd%bf%e7%94%a8php-%e4%be%86%e5%bb%ba%e7%ab%8b-json-objectstring/'
categories:
  - PHP 新手筆記
tags:
  - JSON
  - Json Array
---
有時候有一些**API** / **Web Service** 需要 pass 一些**JSON string** 變數  
那麼怎樣可以在PHP 來建立 **Json Object**/**String**

**解決方法**十分簡單  
我們可以把**Json Object** 的 **property**/屬性 以**Array Object** 的方法來建立  
**E.G.**

<pre>//定義變數
$subValue1= 'subValue1';
    $subValue2= 2;
    
//建立 Array Object
    $jsonVariable = array(
        'arrayProperty1' =&gt; array(
            'subProperty1' =&gt; $subValue1,
            'subProperty2' =&gt; $subValue2
        ),
        'property1' =&gt; 'value1'
    );

            
 //之後我們可以使用 json_encode 來把這個array object轉成 Json String
 echo json_encode($jsonVariable);
</pre>

從前的我可能會用**string concatenation** 的做法 <&#8211;絕對不建議使用這個方法 [反面教材]  
e.g.

<pre>$jsonVar = '{"arrayProperty1":{"' . $subProperty1. '":"subValue1","'.subProperty2.'":2},"property1":"value1"} ';

</pre>

Hope you find it useful