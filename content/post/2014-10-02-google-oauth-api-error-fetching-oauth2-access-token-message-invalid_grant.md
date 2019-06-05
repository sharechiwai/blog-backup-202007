---
id: 3323
title: 'Google OAuth API &#8211; Error fetching OAuth2 access token, message: &#8216;invalid_grant&#8217;'
date: 2014-10-02T00:00:04+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3323
permalink: /2014/10/google-oauth-api-error-fetching-oauth2-access-token-message-invalid_grant/
categories:
  - Google API
tags:
  - OAuth
---
當嘗試使用 **Google OAuth API** 時出現以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Error fetching OAuth2 access token, message: &#8216;invalid_grant&#8217;</strong></span>&#8221;  
<img class="alignnone" src="https://i2.wp.com/farm4.static.flickr.com/3935/15290473669_77fde2e946_z.jpg?resize=440%2C40" alt="Error fetching OAuth2 access token, message: 'invalid_grant'" width="440" height="40" data-recalc-dims="1" /> 

嘗試測試得久..也找不到怎樣解決..  
最後發現..這個錯誤信息的意思 大概是因為**OAuth** return 回來的code 的值 出現問題  
這可能是因為你的程式碼意外地 執行了多過一次..  
令到你嘗試使用**Google OAuth API** 來取得使用者的資料時 這個Code已經不再有效  
E.g. 新Request的Code已經取代了你嘗試使用的 code

**解決方去  
** 要細心看看有沒有什麼地方加了**Google OAuth**的 **Authenticate** 的程式碼 又執行了 多次

Hope you find it useful