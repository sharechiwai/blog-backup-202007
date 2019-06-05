---
id: 3548
title: 'Vagrant Error: SSL certificate problem: unable to get local issuer certificate'
date: 2016-01-15T00:00:21+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=3548
permalink: /2016/01/vagrant-error-ssl-certificate-problem-unable-to-get-local-issuer-certificate/
categories:
  - Vagrant 筆記
tags:
  - Devpos
  - Ubuntu
  - Vagrant
  - Vagrant Troubleshooting
---
想不到一開始使用**Vagrant**便出現問題  
還以為可以很簡單地跟著官網的教學來建立我第一個用**Vagrant**來建立的**Virtual Machine**  
<a href="https://www.vagrantup.com/docs/getting-started/" target="_blank">https://www.vagrantup.com/docs/getting-started/</a>  
誰不知當我嘗試執行以下指令時

<pre>vagrant init hashicorp/precise64
vagrant up
</pre>

出現了以下的錯誤信息  
&#8220;<span style="color: #ff0000;"><strong>Vagrant Error: SSL certificate problem: unable to get local issuer certificate</strong></span>&#8221;

詳情  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1712/24047238074_728a2a7a36_z.jpg?resize=625%2C463" alt="Vagrant Error: SSL certificate problem: unable to get local issuer certificate" width="625" height="463" data-recalc-dims="1" /> 

<pre>D:\Users\Vagrant\DefaultVagrant&gt;vagrant init hashicorp/precise64
A `Vagrantfile` has been placed in this directory. You are now
ready to `vagrant up` your first virtual environment! Please read
the comments in the Vagrantfile as well as documentation on
`vagrantup.com` for more information on using Vagrant.

D:\Users\Vagrant\DefaultVagrant&gt;vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
==&gt; default: Box 'hashicorp/precise64' could not be found. Attempting to find an
d install...
    default: Box Provider: virtualbox
    default: Box Version: &gt;= 0
The box 'hashicorp/precise64' could not be found or
could not be accessed in the remote catalog. If this is a private
box on HashiCorp's Atlas, please verify you're logged in via
`vagrant login`. Also, please double-check the name. The expanded
URL and error message are shown below:

URL: ["https://atlas.hashicorp.com/hashicorp/precise64"]
Error: SSL certificate problem: unable to get local issuer certificate
More details here: http://curl.haxx.se/docs/sslcerts.html

curl performs SSL certificate verification by default, using a "bundle"
 of Certificate Authority (CA) public keys (CA certs). If the default
 bundle file isn't adequate, you can specify an alternate file
 using the --cacert option.
If this HTTPS server uses a certificate signed by a CA represented in
 the bundle, the certificate verification probably failed due to a
 problem with the certificate (it might be expired, or the name might
 not match the domain name in the URL).
If you'd like to turn off curl's verification of the certificate, use
 the -k (or --insecure) option.

</pre>

暫時的**解決方法**十分簡單  
我們可以在剛建立的**Vagrant**資料夾內開啟&#8221;**Vagrantfile**&#8221;  
<img class="alignnone" src="https://i0.wp.com/farm2.static.flickr.com/1534/24581871111_5027628e70_z.jpg?resize=601%2C242" alt="Vagrantfile" width="601" height="242" data-recalc-dims="1" />  
之後加入這句設定來 進行**insecure connection**

<pre># 把Download 設定來 insecure download 便可以暫時解決 SSl Certification verification的問題了
config.vm.box_download_insecure=true;
</pre>

<img class="alignnone" src="https://i2.wp.com/farm2.static.flickr.com/1448/24675418965_e26a368dd7_z.jpg?resize=625%2C239" alt="Vagrant download insecure" width="625" height="239" data-recalc-dims="1" />  
儲存之後再執行

<pre>vagrant up
</pre>

應該便可以起動這個Virtual Machine了

如果大家知道**怎樣可以解決 SSL certification verification** 的問題  
歡迎大家分享

Hope you find it useful