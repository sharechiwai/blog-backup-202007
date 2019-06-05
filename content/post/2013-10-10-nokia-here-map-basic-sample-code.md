---
id: 2967
title: Nokia Here Map Basic Sample Code
date: 2013-10-10T00:00:07+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2967
permalink: /2013/10/nokia-here-map-basic-sample-code/
categories:
  - .Net Tips And Tricks
tags:
  - Nokia Here Map
---
最近想嘗試一下使用**Nokia Here Map.**..  
<http://developer.here.com/>  
自從**Nokia Lumia Windows Phone** 使用 **Nokia Here Map** 之後  
感覺到..他有可能**是Google Map的競爭對手**&#8230;  
聽說**Nokia Map**的**SatNav** 功能很好&#8230;很實用..  
所以便想看看難不難用&#8230;

像我這樣的人當然是喜歡**Copy**他的**Sample Code.**.  
**Load Up** 了他的地圖之後再慢慢嘗試他的功能  
誰不知..他的教學會是希望使用者跟著文章一路讀一路實習&#8230;  
**Javascript API** 的教學文章

不像**Google Map** 一樣可以直接給你複製貼上便可以試  
當我嘗試他的Sample Code時出現了以下的錯誤.做了一會Research 之後才找到解決方法  
原來Javascript 的程式碼 放在 Head Tag 上會出垷以下的錯誤信息的  
&#8220;<span style="color: #ff0000;"><strong>Uncaught TypeError: Cannot read property &#8216;ownerDocument&#8217; of null</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2968" alt="Uncaught TypeError Cannot read property 'ownerDocument' of null" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/Uncaught-TypeError-Cannot-read-property-ownerDocument-of-null.jpg?resize=625%2C71" width="625" height="71" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/10/Uncaught-TypeError-Cannot-read-property-ownerDocument-of-null.jpg)

在**Nokia Here Map** 你需要把**Javascript** 的程式碼放在**Body** Tag 內

為了方便自己/方便大家

以下就是我整理好的**Sample Code**  
大家可以複製之後改了他的<span style="color: #ff0000;"><strong>App_ID</strong> </span>和 <span style="color: #ff0000;"><strong>App_Code</strong></span>便可以使用了

[html]  
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"  
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">  
<html xmlns="http://www.w3.org/1999/xhtml">  
<head>

<meta http-equiv="X-UA-Compatible" content="IE=7; IE=EmulateIE9; IE=10" />  
<script src="http://js.api.here.com/se/2.5.3/jsl.js" type="text/javascript" charset="utf-8"></script>  
<style type="text/css">  
html {  
overflow:hidden;  
}

body {  
margin: 0;  
padding: 0;  
position: absolute;  
overflow:hidden;  
width: 100%;  
height: 100%;  
}

#mapContainer {  
width: 100%;  
height: 100%;  
left: 0;  
top: 0;  
position: absolute;  
}  
</style>

</head>  
<body>  
<div id="mapContainer"></div>  
<script type="text/javascript">  
nokia.Settings.set("app_id", "[YOUR APP ID]");  
nokia.Settings.set("app_code", "[YOUR APP CODE]");

var map = new nokia.maps.map.Display(  
document.getElementById("mapContainer"), {  
// Zoom level for the map  
zoomLevel: 10,  
// Map center coordinates  
center: [52.51, 13.4]  
}  
);  
</script>  
</body>  
</html>  
[/html]

Hope you find it useful