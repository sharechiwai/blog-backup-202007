---
id: 2776
title: 'Edit StyleCop Settings &#8211; StyleCop &#8211; SA1126 &#8211; Disable some of the StyleCop Rules &#8211;  停用某些StyleCop的規則'
date: 2013-04-19T02:46:57+08:00
author: ShareChiWai
layout: post
guid: http://blog.sharechiwai.com/?p=2776
permalink: '/2013/04/edit-stylecop-settings-stylecop-sa1126-disable-some-of-the-stylecop-rules-%e5%81%9c%e7%94%a8%e6%9f%90%e4%ba%9bstylecop%e7%9a%84%e8%a6%8f%e5%89%87/'
categories:
  - StyleCop
tags:
  - SA1126
---
今天繼續嘗試把 **ASP.Net MVC** 的**Project** 的Code 轉成 乎合 **StyleCop** 和 **Resharper**的**Coding Standard**的 程式碼&#8230;  
誰不知遇到一個 **StyleCop** 提出 警告

&#8220;<span style="color: #ff0000;"><strong>SA1126 : CSharp.Readability : The call to Session must begin with the &#8216;this.&#8217;, &#8216;base.&#8217;, &#8216;object.&#8217; or &#8216;ContactController.&#8217; or &#8216;Controller.&#8217; prefix to indicate the intended method call.</strong></span>&#8221;

和

&#8220;<span style="color: #ff0000;"><strong>SA1126 : CSharp.Readability : The call to View must begin with the &#8216;this.&#8217;, &#8216;base.&#8217;, &#8216;object.&#8217; or &#8216;ContactController.&#8217; or &#8216;Controller.&#8217; prefix to indicate the intended method call.</strong></span>&#8221;

[<img class="alignnone size-full wp-image-2777" alt="SA1126 : CSharp.Readability : The call to View must begin with the 'this.', 'base.'" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1126.png?resize=625%2C100" width="625" height="100" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/SA1126.png)  
我的程式碼是這樣的:

[csharp]  
public ActionResult Index()  
{  
if (Session["UserInfo"] == null || Session["UserInfo"].ToString() != contactInfo.Name)  
{

return View("Error");  
}  
return View();  
}  
[/csharp]

當我把程式碼上的**View** 和 **Session** 前加上了 &#8220;**this.**&#8221;  
**StyleCop**的警告便消失了

但是 **Resharper**卻出現了警告信息:  
&#8220;<span style="color: #ff0000;"><strong>Qualifier &#8216;this.&#8217; is redundant</strong></span>&#8221;  
[<img class="alignnone size-full wp-image-2778" alt="Qualifier This Is Redundant" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/QualifierThisIsRedundant.png?resize=625%2C152" width="625" height="152" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/QualifierThisIsRedundant.png)

在這個情況下..**Resharper**有他的道理&#8230;  
所以我便希望改變StyleCop的規定去適合自己的喜好 和適合**Resharper**的設定了

嘗試找**StyleCop** 的設定很久很久..終於找到了..

**解決方法**:  
原來只有在**Project**上按 &#8220;**滑鼠右鍵**/ **Mouse Right Click**&#8221;  
之後在選單上選擇 &#8220;**StyleCop Settings**&#8221;  
[<img class="alignnone size-full wp-image-2779" alt="StyleCop Settings Options" src="https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopSettingsOptions.png?resize=625%2C225" width="625" height="225" data-recalc-dims="1" />](https://i1.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopSettingsOptions.png)

之後便會看到 &#8220;**StyleCop Project Settings**&#8221; 的視窗  
由於這些規則是以屬性類型來分類的..  
所以十分方便  
[<img class="alignnone size-full wp-image-2780" alt="StyleCop Project Settings" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopProjectSettings.png?resize=625%2C480" width="625" height="480" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopProjectSettings.png)

以我的例子:  
警告是和**CSharp.Readability** 相關的  
我便可以按一下**Readability** 的 **Member Access**相關的 開啟了相關的 Folder便 看到了 **SA1126**  
只要把他**untick** 便可以停用他了  
完成後按一下&#8221;**確定**/**OK**&#8221; 便可以了  
[<img class="alignnone size-full wp-image-2781" alt="StyleCop Project Settings Disable - SA1126" src="https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopProjectSettingsDisableSA1126.png?resize=625%2C480" width="625" height="480" data-recalc-dims="1" />](https://i0.wp.com/blog.sharechiwai.com/wp-content/uploads/2013/05/StyleCopProjectSettingsDisableSA1126.png)

再次執行**StyleCop**這個警告便不見了

*由於這個設定是以**Project**為單位的.. 你可能要幫每一個**Project**都要這樣停用某些規則才能解決..  
有時間的話..希望可以和大家分享&#8230;如何更變**StyleCop的設定** 令到只需要更變一個設定檔便可以解決所有Project的問題

Hope you find it useful