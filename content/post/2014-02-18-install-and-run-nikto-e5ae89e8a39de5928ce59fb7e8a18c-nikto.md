---
id: 3080
title: 'Install and Run Nikto &#8211; 安裝和執行 Nikto'
date: 2014-02-18T00:00:03+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3080
permalink: '/2014/02/install-and-run-nikto-%e5%ae%89%e8%a3%9d%e5%92%8c%e5%9f%b7%e8%a1%8c-nikto/'
categories:
  - Security/電腦保安
tags:
  - Linux
  - Ubuntu
---
**Nikto**是一個可以給你查看**Remote Web Server** 的設定的程式..  
他可以給你一個小小的保安報告..  
令你可以修正你的**Web Application** 或 **Web Server** 的設定

以下是 **Install and Run Nikto** &#8211; **安裝和執行 Nikto 的方法**

首先要在**GitHub** 上取得最新的**Nikto**  
**Nikto** 在**GitHub**的網址是  
<a title="Nikto Github Link" href="https://github.com/sullo/nikto.git" target="_blank">https://github.com/sullo/nikto.git</a>

大家可以在 **Terminal** 上  
輸人

&#8220;<span style="color: #008000;"><strong>git clone https://github.com/sullo/nikto.git nikto</strong></span>&#8221;

完成後去 剛從Git 建立的資料夾 &#8220;**nikto**&#8220;內的&#8221;**program**&#8220;資料夾

E.g.  
&#8220;<span style="color: #008000;"><strong>cd nikto/program</strong></span>&#8221;

執行 **Nikto**  
&#8220;<span style="color: #008000;"><strong>perl nikto.pl -host http://網址.com</strong></span>&#8221;

之後便會看到這個Web Server的資訊了

更多有關怎樣使用Nikto的資料可以參考以下網頁  
<a title="More information related with Nikto" href="https://github.com/sullo/nikto" target="_blank">https://github.com/sullo/nikto</a>

Hope you find it useful