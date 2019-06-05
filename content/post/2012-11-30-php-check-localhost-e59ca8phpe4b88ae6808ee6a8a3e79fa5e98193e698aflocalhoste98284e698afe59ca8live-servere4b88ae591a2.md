---
id: 2625
title: 'PHP check localhost &#8212; 在PHP上怎樣知道是Localhost還是在Live Server上呢?'
date: 2012-11-30T00:00:10+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2625
permalink: '/2012/11/php-check-localhost-%e5%9c%a8php%e4%b8%8a%e6%80%8e%e6%a8%a3%e7%9f%a5%e9%81%93%e6%98%aflocalhost%e9%82%84%e6%98%af%e5%9c%a8live-server%e4%b8%8a%e5%91%a2/'
categories:
  - PHP 新手筆記
---
最近多了使用**PHP**開發Website  
很多時候.因為安全問題的關係  
在開發時使用的**設定**和在**Production** 上的設定是不一樣的

為了方便自己可以不用人手更變設定的關係..  
我便嘗試找出怎樣在PHP 上找出自己現在是**在Local Host**還是**LIVE Server**上了  
**解決方法**:

我在可以使用一個**IF Statement**來檢查一下自己的**Server Address** 是什麼.  
如果是 **127.0.0.1** **IPv4** 或**1 ::1** **IPv6** 的**Local IP Address**  
那我們使是在使用**LocalHost**了

[php]  
function IsLocal(){  
if(in\_array($\_SERVER["SERVER_ADDR"],array("127.0.0.1","::1")))  
{  
return true;

}else{  
return false;  
}  
}

if(IsLocal()){  
echo "dev setting to be load";  
}else{  
echo "live setting to be load";  
}

[/php]

Hope you find it useful