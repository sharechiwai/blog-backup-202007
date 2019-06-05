---
id: 1848
title: 'PHP Connect to MSSQL Issue 2 &#8211; Warning mssql_connect()[function.mssql-connect]: Unable to connect to server: &#8211; PHP 連接MSSQL Database 問題 2'
date: 2011-05-25T00:00:16+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=1848
permalink: '/2011/05/php-connect-to-mssql-issue-2-warning-mssql_connectfunction-mssql-connect-unable-to-connect-to-server-php-%e9%80%a3%e6%8e%a5mssql-database-%e5%95%8f%e9%a1%8c-2/'
categories:
  - PHP 新手筆記
tags:
  - MSSQL
  - XAMPP
---
當所有和**MSSQL** 有關的設定的也設定好之後  
我還是不能成功連接到**MSSQL**..  
在連接時出現這個問題  
&#8220;<span style="color: #ff0000;"><strong>Warning mssql_connect()[function.mssql-connect]: Unable to connect to server:</strong></span>&#8221;  
[<img class="alignnone" title="Warning mssql_connect()[function.mssql-connect]: Unable to connect to server" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/48f0e6ad0a5044968f2acb21812eb4dc/renditions/fullsize.jpg?resize=550%2C115" alt="" width="550" height="115" data-recalc-dims="1" />](https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/48f0e6ad0a5044968f2acb21812eb4dc/renditions/fullsize.jpg)

為了確定問題不在於**Server**的關係..  
我用了**Microsoft SQL Server Management Studio**  
來連接這個**Remote的SQL Server**  
成功連線..証明了問題不在Server上

所以便要好好研究一下我的**PHP code/PHP settings** 那裡出現問題  
最後發現有可能要 **Apache/PHP** 中其中一個**DLL** 出現了問題

**解決方法**  
你可以到以下URL 下載 **<span style="color: #3366ff;">ntwdblib.dll<br /> </span>**<http://l.lookfor.hk/SkyDriveMain>  
之後把他複製/取代 你電腦上的  
**<span style="color: #3366ff;">Apache/bin/ntwdblib.dll<br /> <a href="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0125b5ed30294af2a535e3f06735e87c/renditions/fullsize.jpg"><img class="alignnone" title="Apache Bin Folder" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0125b5ed30294af2a535e3f06735e87c/renditions/fullsize.jpg?resize=596%2C448" alt="" width="596" height="448" data-recalc-dims="1" /></a></span>**  
E.G.  
<span style="color: #3366ff;"><strong>H:\xampp\Apache/bin/ntwdblib.dll</strong></span>  
和  
**<span style="color: #3366ff;">php/ntwdblib.dll<br /> <a href="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a2780de065184c899a8af381f71a03f7/renditions/fullsize.jpg"><img class="alignnone" title="Php Ext folder" src="https://i0.wp.com/api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/a2780de065184c899a8af381f71a03f7/renditions/fullsize.jpg?resize=596%2C412" alt="" width="596" height="412" data-recalc-dims="1" /></a></span>**  
E.g.  
<span style="color: #3366ff;"><strong>H:\xampp\php\ext\ntwdblib.dll</strong></span>  
[在取代前我會建議你先備份這兩個資料夾上的**<span style="color: #3366ff;">ntwdblib.dll</span>** 以防萬一]

還有一個要注意的地方  
就是雖然 **MSSQL Server 的 default port 是 1433**  
但是我們寫的**php code**時需要加上這個**Port** 的

在**Windows**的系統下  
和在程式碼上我們要在**Server Address** 後面加上&#8221;**,**&#8221; 之後再加上**1433**  
而不是不常用問的”:”  
E.g.

[php]  
$conn = mssql\_connect("sharechiwai\_server,1433", "sharechiwai" "Password")  
or die("Couldn&#8217;t connect to SQL Server on $myServer");

if (!$conn) {  
die(&#8216;Something went wrong while connecting to MSSQL&#8217;);  
}  
[/php]

而在**Linux**的系統上我們在**Server Address** 後面加上&#8221;:&#8221; 之後再加上**1433  
** E.G.

[php]  
$conn = mssql\_connect("sharechiwai\_server:1433", "sharechiwai" "Password")  
or die("Couldn&#8217;t connect to SQL Server on $myServer");

if (!$conn) {  
die(&#8216;Something went wrong while connecting to MSSQL&#8217;);  
}  
[/php]

Hope you find it useful