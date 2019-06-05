---
id: 2169
title: 'Setup Git for BitBucket on Windows Part II &#8211; 在Windows 上設定Git Part II'
date: 2011-11-08T00:00:13+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2169
permalink: '/2011/11/setup-git-for-bitbucket-on-windows-part-ii-%e5%9c%a8windows-%e4%b8%8a%e8%a8%ad%e5%ae%9agit-part-ii/'
categories:
  - Experience Share / 經驗分享
tags:
  - BitBucket
  - Git
---
在開始使用前我們需要先建立一個**SSH Key** 來和 **Server**連線的

**開始建立我們的SSH Key**

首先我們按&#8221;**Start Menu/開始**&#8221; ->&#8221;**Git**&#8220;資料夾 ->選擇 &#8220;**Git Bash**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/f1a914408ed3450b94dc00cc8c766e71" alt="Start Menu -> Git -> Git Bash&#8221; width=&#8221;251&#8243; height=&#8221;145&#8243; />  
之後我們可以使用以下的**Command** 查看我們之前有沒有建立過 **SSH Key**  
&#8220;**cd ~/.ssh**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/cec26873992b414cae788990dbd06ab9" alt="cd ~/.ssh No such file or directory" width="572" height="161" />  
如果結果是這樣的話&#8221;**No such file or directory**&#8221; 意思是你電腦上沒有建立過**SSH key**

[如果有的話.. 可以考慮到你電腦上的**User Profile**上 **backup**了他..E.G. 把這**.ssh** 這個資料夾改名便可以了]  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/018ba600377e4d62ab6e6b33308d8088" alt="User folder" width="422" height="265" /> 

我們可以使用以下的指令去建立自己的SSH Key  
&#8220;**ssh-keygen -t rsa -C &#8216;youremail@youremailaddress.com&#8217;**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e227c2bdfafa4236875bccd75c5afa49" alt="generate ssh key command ssh-keygen -t rsa -C email address" width="566" height="156" />  
[請用自己在**BitBucket**上的**email來取締** &#8220;**youremail@youremailaddress.com**&#8221; ]  
按&#8221;**Enter**&#8221; 之後 便會叫你輸入一個檔案名用來儲存你的**SSH Key**..  
我們不用輸入檔案名..真接按&#8221;Enter&#8221; 便可以了

之後便會叫你輸入&#8221;**passphrase**&#8221; (和密碼差不多的東西)  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/e2c8902f545f41c383e213f4d522bb08" alt="Enter passphrase" width="604" height="219" />  
輸入之後按&#8221;**Enter**&#8221; 重複輸入 自己定下的&#8221;**passphrase**&#8221; 之後  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d67bb0875dff4918a1ea0b64c87e3df0" alt="Enter Passphrase again" width="590" height="230" />  
你便應該可以看到和下面差不多的畫面..  
說明了你的**Private Key** 和**Public key** 儲存了在那裡  
和你的**SSH** 指紋是怎樣的..等等  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/8277ac61b4704691b4400f956b19fcf6" alt="generated public and private ssh key with fingerprint" width="597" height="291" />  
現在你的**SSH Key** 已經建立了..

之後我們便需要把我們的**Public Key**加進我們的**BitBucket Account**上了..  
我們可以執行以下&#8221;**Command/指令**&#8221;  去檢查能不能連接到 **BitBucket**的**Account** 上  
&#8220;**ssh -T git@bitbucket.org**&#8221;

如果我們沒有把**Public key** 加到**BitBucket** 上時..  
我們會遇到以下的錯誤信息..&#8221;**Permission Denied (publickey)**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/359a5c2aa809405f8f1b0e8f46fb3608" alt="Permission Denied (Public key)" width="662" height="402" />  
所以我們先要登入我們的 **BitBucket Account**..  
之後用mouse 指向自己的**用戶名稱**->選擇&#8221;**Account**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/3b4826f2a39a415a8676b3f49a8b3bf4" alt="bitbucket account setting" width="309" height="216" /> 

之後我們可以打開之前自己建立的**SSH Key**的**Public Key**檔案..[**id_rsa.pub**]  
他的位置應該會在你的使用者資料來內的..  
當你到&#8221;**Start Menu/開始**&#8221; -> 選擇你的&#8221;**使用者名稱**&#8221;  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/018ba600377e4d62ab6e6b33308d8088" alt="User folder" width="422" height="265" /> 

開啟&#8221;.ssh&#8221;資料夾便可以看到之前所產生的**SSH Key** 檔案了  
**id_rsa** 是**Private Key**  
**id_rsa.pub** 是** Public Key**  
**known_hosts** 是用來儲存我們容許連接到的IP address  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/70b25b08c8b64390b4f3650bc317cd64" alt="ssh key files" width="548" height="199" /> 

我們可以使用&#8221;**Notepad/記事簿**&#8221; 開啟我們的Public Key [id_rsa.pub] 檔案..  
之後複製檔案內的所有內容  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/731bc65f3ebf445380116f6499e52f83" alt="Open id_rsa.pub with notepad" width="686" height="308" />  
之後我們便回到**BitBucket** 我們的Account Setting 上  
找到了**SSH Keys** 的**Section**  
在這個TextBox上貼上你剛剛複製的Public Key內容  
之後按&#8221;**Add Key**&#8220;..  
完成後要記著按&#8221;**Save**&#8221; 去儲存**BitBucket**上的設定  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/0e3a870980654d27b9a89ec977e063d2" alt="Add SSH public key to BitBucket" width="504" height="183" /> 

之後我們可以返回我們的&#8221;**Git Bash/ Command Prompt**&#8221; 畫面

再次執行之前的指令/command  
&#8220;**ssh -T git@bitbucket.org**&#8221;  
之後他會顯示&#8221;**Warning: Permanently added the RSA host key for IP address &#8216;xxx.xxx.xxx.xxx&#8217; to the list of known hosts**&#8221;  
之後便會叫我們輸入我們之前所設定的&#8221;**passphrase**&#8221; 了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/896c76c0c77c4955a9d76f53552a24a9" alt="Successfully connect to BitBucket" width="665" height="156" /> 

有輸入&#8221;**passphrase**&#8221; 這個畫面證明了..我們設定的**SSH key** 已經成功建立..  
我們便可以開始使用**BitBucket** 作為我們**Source control**/或**Backup source code** 的地方了  
<img src="http://api.photoshop.com/v1.0/accounts/aa9037104a014abbb11ad4bd58324b91/assets/d4383a595d7f479ab4ad45e8f62509d8" alt="Successfully connect to BitBucket however it has syntax error" width="676" height="184" /> 

輸入完**Passphrase**之後出現&#8221;**Invalid command syntax**&#8221; 是正常的

將來有時間的話..我會寫多一些怎樣使用**Git**的網誌..

Hope you find it useful