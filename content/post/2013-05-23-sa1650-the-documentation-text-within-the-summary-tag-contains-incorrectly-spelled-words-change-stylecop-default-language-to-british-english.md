---
id: 2913
title: 'SA1650: The documentation text within the summary tag contains incorrectly spelled words &#8211; Change StyleCop default language to British English'
date: 2013-05-23T17:43:03+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2913
permalink: /2013/05/sa1650-the-documentation-text-within-the-summary-tag-contains-incorrectly-spelled-words-change-stylecop-default-language-to-british-english/
categories:
  - StyleCop
---
在填寫 **Documentation Header** 時  
**StyleCop** 出現了以下的**Warning**  
&#8220;<span style="color: #ff0000;"><strong>The documentation text within the summary tag contains incorrectly spelled words: initialise</strong></span>&#8220;[<img class="alignnone size-full wp-image-2915" alt="SA1650 The documentation text within the summary tag contains incorrectly spelled words: initialise" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SA1650_BritishEng.png?resize=625%2C109" width="625" height="109" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/SA1650_BritishEng.png)

**Initialise** 是沒有寫錯的..  
所以相信這應該是 **StyleCop** 設定上字典的語言 問題  
E.G. 應該是使用了 **en-us** 美式英語.. 而我用的是英式英語 **en-gb**  
美式英語是這樣寫的 &#8220;**Initialize**&#8221;  
而英式卻時這樣 &#8220;**Initialise**&#8221;

為了避免語言寫法問題再次出現**warning**解決方法是嘗試更改**StyleCop**的預設語言 的值

**解決方法:**

原來只有在Project上按 “**滑鼠右鍵**/ **Mouse Right Click**”  
之後在選單上選擇 “**StyleCop Settings**”  
[<img alt="StyleCop Settings Options" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopSettingsOptions.png?resize=625%2C225" width="625" height="225" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopSettingsOptions.png)

在&#8221;**Options Tab** / **選項分頁**&#8221; 上的 &#8220;**Culture for analysis**&#8221; 上選擇 &#8220;**en-GB**&#8221; 後按 &#8220;**OK** / **確定**&#8220;便可  
[<img class="alignnone size-full wp-image-2914" alt="StyleCop Change Default Language" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/StyleCopSettingsOptionLanguage.png?resize=625%2C498" width="625" height="498" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/09/StyleCopSettingsOptionLanguage.png)

再次執行 **StyleCop** 之後 **Warning SA1650** 便消失了

Hope you find it useful