---
id: 2383
title: JQuery Button Click Event / JQuery 上的 Button Click Event
date: 2012-04-26T00:00:51+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2383
permalink: '/2012/04/jquery-button-click-event-jquery-%e4%b8%8a%e7%9a%84-button-click-event/'
categories:
  - Jquery Notes
tags:
  - JQuery CheckSheet
---
使用**JQuery** 其中一個十分常用的功能相信是 **button click**這個動作&#8230;  
使用方法十分簡單

我們要預先在**Document.Ready**的 **Event**上先定義一下 將來會做的動作  
E.G Button Click  
//定義 這個**Button Click Event**  
我們多數會使用 ID 來選擇我們要控制那一個Control的  
在Jquery上 要選擇一個Control我們可以使用  
$(&#8220;#ID名稱&#8221;) 便可以了  
**Javascript**

[javascript]  
<script type="text/javascript">  
$(document).ready(function () {

//以下定義了當 按鈕 "btn_Run", 有人Click的時候便彈出一個Hello ShareChiWai的MessageE.G.  
$("#btn_Run").click(function(){  
alert("Hello! ShareChiWai.");  
});

});  
</script>  
[/javascript]

**HTML**

[html]  
<input type="button" id="btn_Run" value="Run"/>  
[/html]

十分簡單

//**click()** 這一個功能不是只限於Button的.. 其他是很多東西也可以使用的  
E.G. **Div**  
**HTML**

[html]  
<div id="div_ClickSample">  
Click Sample  
</div>  
[/html]

**Javascript**

[javascript]  
<script type="text/javascript">  
$(document).ready(function () {

$("#div_ClickSample").click(function(){  
alert("Hello! You Just Clicked on a Div");  
});

});  
</script>  
[/javascript]

Hope you find it useful