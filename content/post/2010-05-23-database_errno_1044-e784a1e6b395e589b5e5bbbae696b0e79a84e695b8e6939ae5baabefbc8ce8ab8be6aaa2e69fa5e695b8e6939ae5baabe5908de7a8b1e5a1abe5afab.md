---
id: 119
title: database_errno_1044 無法創建新的數據庫，請檢查數據庫名稱填寫是否正確
date: 2010-05-23T00:00:00+08:00
author: ShareChiWai
layout: post
guid: 'http://sharechiwai.wordpress.com/2010/05/23/database_errno_1044-%e7%84%a1%e6%b3%95%e5%89%b5%e5%bb%ba%e6%96%b0%e7%9a%84%e6%95%b8%e6%93%9a%e5%ba%ab%ef%bc%8c%e8%ab%8b%e6%aa%a2%e6%9f%a5%e6%95%b8%e6%93%9a%e5%ba%ab%e5%90%8d%e7%a8%b1%e5%a1%ab%e5%af%ab'
permalink: '/2010/05/database_errno_1044-%e7%84%a1%e6%b3%95%e5%89%b5%e5%bb%ba%e6%96%b0%e7%9a%84%e6%95%b8%e6%93%9a%e5%ba%ab%ef%bc%8c%e8%ab%8b%e6%aa%a2%e6%9f%a5%e6%95%b8%e6%93%9a%e5%ba%ab%e5%90%8d%e7%a8%b1%e5%a1%ab%e5%af%ab/'
blogger_blog:
  - sharechiwai.blogspot.com
blogger_author:
  - 智/Chi
blogger_242190872ae71f6d0f1f8731ec21ccf3_permalink:
  - "587381509560572507"
categories:
  - 電腦小貼事 Computing Tips and Tricks
---
今日有朋友給了我一個機會在他的web-hosting 入面設定 **Discuz forum**&#8230;  
他在SETUP **Discuz forum**時有些困難  
當他輸入了數據庫服務器/用戶名/密碼/數據庫名 等等的資料後  
便出現了這個error message  
&#8220;**database\_errno\_1044 無法創建新的數據庫，請檢查數據庫名稱填寫是否正確**&#8220;

<div class="separator" style="clear:both;text-align:center;">
  <a href="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/discuz.jpg" style="margin-left:1em;margin-right:1em;"><img border="0" height="391" src="https://i2.wp.com/oldblog.sharechiwai.com/wp-content/uploads/2010/08/discuz.jpg?resize=625%2C391" width="625" data-recalc-dims="1" /></a>
</div>

我可以在**PHPMyAdmin** 中看到這個數據庫&#8230;  
所有設定看來都沒有問題&#8230;E.G. 所有CONFIG.INI 都沒有問題

之後我便登入到他的Web-hosting 的control panel  
最後發現原來他CREATE 了DATABASE USER 但沒有 ASSIGN 權利給他  
所以便有這個ERROR 了&#8230;  
E.G. 因為當使用這個DATABASE 的用戶資料來登入時&#8230;  
是找不到這個DATABASE 的&#8230;

解決方法:  
只要去Web-hosting 的**control panel** &#8212;>Database section 入面  
設定返 使用者權限  
給與這個database-user可以有**CREATE**/**SELECT**等等的Database 權限  
便可以了

Good Luck =)