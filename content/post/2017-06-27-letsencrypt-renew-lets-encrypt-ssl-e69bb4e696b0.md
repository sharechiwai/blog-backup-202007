---
id: 4006
title: 'LetsEncrypt Renew &#8211; Lets Encrypt SSL 更新'
date: 2017-06-27T06:51:11+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=4006
permalink: '/2017/06/letsencrypt-renew-lets-encrypt-ssl-%e6%9b%b4%e6%96%b0/'
categories:
  - UBuntu
tags:
  - LetsEncrypt
  - SSL
  - Ubuntu
  - VPS
---
差不多每三個月 **Let&#8217;s Encrypt Expiry Bot**  
便會**Email** 我說.. 我的**SSL** 後快便會到期**Expire**  
我需要去**Renew**&#8230;  
[<img class="alignnone size-large wp-image-4009" src="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptExpiry.png?resize=625%2C39" alt="Let's Encrypt Expiry Bot Email Notification" width="625" height="39" srcset="https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptExpiry.png?resize=1024%2C64 1024w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptExpiry.png?resize=300%2C19 300w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptExpiry.png?resize=768%2C48 768w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptExpiry.png?resize=624%2C39 624w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptExpiry.png?w=1465 1465w, https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptExpiry.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i2.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptExpiry.png)

**解決方法**十分簡單  
我們只需要在server 的**Terminal** 上用 **sudo**執行以下指令便可

<pre>sudo certbot-auto renew
</pre>

[<img class="alignnone size-large wp-image-4007" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptRenew.png?resize=625%2C339" alt="Let's Encrypt Renew Successfully" width="625" height="339" srcset="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptRenew.png?resize=1024%2C555 1024w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptRenew.png?resize=300%2C163 300w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptRenew.png?resize=768%2C416 768w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptRenew.png?resize=624%2C338 624w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptRenew.png?w=1358 1358w, https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptRenew.png?w=1250 1250w" sizes="(max-width: 625px) 100vw, 625px" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2017/06/letsEncryptRenew.png)

完成後會說成功renew

hope you find it useful