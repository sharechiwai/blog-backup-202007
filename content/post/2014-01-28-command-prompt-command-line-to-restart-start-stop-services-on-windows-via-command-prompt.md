---
id: 3025
title: Command Prompt / Command line to restart , Start , Stop Services on Windows via Command Prompt
date: 2014-01-28T00:00:49+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3025
permalink: /2014/01/command-prompt-command-line-to-restart-start-stop-services-on-windows-via-command-prompt/
categories:
  - 電腦小貼事 Computing Tips and Tricks
tags:
  - Batch File
  - Command Prompt
---
最近公司開發一個應該程式需要連接到**FTP** 上的  
所以我們便安裝了一個**FTP Service**  
可惜每修改了 **FTP** 的設定之後..需要重新啟動 這個FTP Services  
<img class="alignnone" alt="Administrative Tools -> Services" src="https://i1.wp.com/farm4.staticflickr.com/3770/12499313965_f622ccb981_z.jpg?resize=625%2C255" width="625" height="255" data-recalc-dims="1" />  
由于每次有所更新都要 開啟  
&#8220;**Control Panel**&#8221; -> **&#8220;Administrative Tools**&#8221; ->&#8221;**Services**&#8221; 選擇那個**Service** 的名稱..之後進行&#8221;**重新啟動**&#8221;  
太麻煩了

所以便想寫一個**Batch File** 放在**Desktop**..放便自己可以**Restart Services**  
之後便不用常常開啟 &#8220;**Control Panel**&#8221; -> &#8220;**Administrative Tools**&#8221; ->&#8221;**Services**&#8220;..  
上去&#8221;**重新啟動**&#8220;他們了

停用和啟用服務的 **Command** 是這樣的

**啟用**  
**net start** &#8220;[**Service name** / **服務名**]&#8221;

**停用**  
**net stop** &#8220;[**Service name** / **服務名**]&#8221;

如果想**restart** / **重新啟動**的話便要先執行 停用之後執行 啟用 的 **Command** 了

請注意..你有可能需要有管理員權限可以使用這個Command的  
<span style="color: #ff0000;"><strong>Access is Denied</strong></span>  
<img class="alignnone" alt="Access is denied  - Run as Administrator needed" src="https://i1.wp.com/farm4.staticflickr.com/3814/12499314025_9b1b45bb76_z.jpg?resize=502%2C238" width="502" height="238" data-recalc-dims="1" /> 

以下是我**Batch** file的 Sample. [我需要**重新啟動 WindSFTP 這個服務**]

[code]  
net stop WindSFTP  
net start WindSFTP  
pause  
[/code]

**Pause** &#8211; 這個Command 主要是把**Command prompt**這個Screen 留下來  
否則當他執行完**Command**後便會自動消失..  
由於太快的關係..所以你都不知道在 執行過程中有沒有錯誤..

<img class="alignnone" alt="Restart Services WindSFTP" src="https://i2.wp.com/farm6.staticflickr.com/5541/12499442093_b93a9ee41a_z.jpg?resize=501%2C221" width="501" height="221" data-recalc-dims="1" />  
Hope you find it useful